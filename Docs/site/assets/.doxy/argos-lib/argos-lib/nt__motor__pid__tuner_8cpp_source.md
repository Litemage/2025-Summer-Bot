

# File nt\_motor\_pid\_tuner.cpp

[**File List**](files.md) **>** [**argos\_lib**](dir_f9cbf5730473812e84551a5945ef39f8.md) **>** [**cpp**](dir_cf4b00708d9639a2579b4441eb30ca52.md) **>** [**general**](dir_16b6c439f6536703101f25e459a4699b.md) **>** [**nt\_motor\_pid\_tuner.cpp**](nt__motor__pid__tuner_8cpp.md)

[Go to the documentation of this file](nt__motor__pid__tuner_8cpp.md)


```C++


#include "argos_lib/general/nt_motor_pid_tuner.h"

#include <array>
#include <chrono>

#include "frc/smartdashboard/SmartDashboard.h"

using namespace std::literals::chrono_literals;

using argos_lib::ClosedLoopSensorConversions;
using argos_lib::NTMotorPIDTuner;

NTMotorPIDTuner::NTMotorPIDTuner(const std::string& tableName,
                                 std::initializer_list<BaseTalon*> motors,
                                 unsigned pidSlot,
                                 ClosedLoopSensorConversions sensorConversions)
    : m_updateSubscriber{tableName}
    , m_pMotors{motors}
    , m_pidSlot{pidSlot}
    , m_pntTable(nt::NetworkTableInstance::GetDefault().GetTable(tableName))
    , m_sensorConversions{sensorConversions}
    , m_threadMutex()
    , m_threadStopCv()
    , m_statusUpdateThread{[this]() { UpdateClosedLoopMonitoringThread(); }} {
  m_activeConfigs.SlotNumber = m_pidSlot;
  if (!std::empty(motors)) {
    (*motors.begin())->GetConfigurator().Refresh(m_activeConfigs);
  }

  m_updateSubscriber.AddMonitor(
      "tunes/kP",
      [this](double newVal) {
        for (auto motor : m_pMotors) {
          m_activeConfigs.kP = newVal;
          motor->GetConfigurator().Apply(m_activeConfigs, 50_ms);
        }
      },
      m_activeConfigs.kP);
  m_updateSubscriber.AddMonitor(
      "tunes/kI",
      [this](double newVal) {
        for (auto motor : m_pMotors) {
          m_activeConfigs.kI = newVal;
          motor->GetConfigurator().Apply(m_activeConfigs, 50_ms);
        }
      },
      m_activeConfigs.kI);
  m_updateSubscriber.AddMonitor(
      "tunes/kD",
      [this](double newVal) {
        for (auto motor : m_pMotors) {
          m_activeConfigs.kD = newVal;
          motor->GetConfigurator().Apply(m_activeConfigs, 50_ms);
        }
      },
      m_activeConfigs.kD);
  m_updateSubscriber.AddMonitor(
      "tunes/kV",
      [this](double newVal) {
        for (auto motor : m_pMotors) {
          m_activeConfigs.kV = newVal;
          motor->GetConfigurator().Apply(m_activeConfigs, 50_ms);
        }
      },
      m_activeConfigs.kV);
  m_updateSubscriber.AddMonitor(
      "tunes/kA",
      [this](double newVal) {
        for (auto motor : m_pMotors) {
          m_activeConfigs.kA = newVal;
          motor->GetConfigurator().Apply(m_activeConfigs, 50_ms);
        }
      },
      m_activeConfigs.kA);
  m_updateSubscriber.AddMonitor(
      "tunes/kS",
      [this](double newVal) {
        for (auto motor : m_pMotors) {
          m_activeConfigs.kS = newVal;
          motor->GetConfigurator().Apply(m_activeConfigs, 50_ms);
        }
      },
      m_activeConfigs.kS);
  m_updateSubscriber.AddMonitor(
      "tunes/kG",
      [this](double newVal) {
        for (auto motor : m_pMotors) {
          m_activeConfigs.kG = newVal;
          motor->GetConfigurator().Apply(m_activeConfigs, 50_ms);
        }
      },
      m_activeConfigs.kG);
  m_updateSubscriber.AddMonitor(
      "tunes/GArm",
      [this](double newVal) {
        for (auto motor : m_pMotors) {
          m_activeConfigs.GravityType = newVal == 0 ? ctre::phoenix6::signals::GravityTypeValue::Elevator_Static :
                                                      ctre::phoenix6::signals::GravityTypeValue::Arm_Cosine;
          motor->GetConfigurator().Apply(m_activeConfigs, 50_ms);
        }
      },
      m_activeConfigs.GravityType == ctre::phoenix6::signals::GravityTypeValue::Arm_Cosine);
}

NTMotorPIDTuner::~NTMotorPIDTuner() {
  m_threadStopCv.notify_all();
  m_statusUpdateThread.join();
}

void NTMotorPIDTuner::UpdateClosedLoopMonitoringThread() {
  bool keepRunning = true;

  std::vector<double> setpoints;
  std::vector<double> positions;
  std::vector<double> velocities;
  std::vector<double> outputs;
  std::vector<double> errors;

  setpoints.reserve(m_pMotors.size());
  positions.reserve(m_pMotors.size());
  velocities.reserve(m_pMotors.size());
  outputs.reserve(m_pMotors.size());
  errors.reserve(m_pMotors.size());

  while (keepRunning) {
    std::unique_lock<std::mutex> lock{m_threadMutex};
    if (m_threadStopCv.wait_for(lock, 50ms) == std::cv_status::no_timeout) {
      keepRunning = false;
    } else {
      setpoints.clear();
      positions.clear();
      velocities.clear();
      outputs.clear();
      errors.clear();
      for (auto motor : m_pMotors) {
        const auto controlMode = motor->GetControlMode().GetValue();
        switch (controlMode.value) {
          case ctre::phoenix6::signals::ControlModeValue::PositionDutyCycle:
          case ctre::phoenix6::signals::ControlModeValue::VelocityDutyCycle:
          case ctre::phoenix6::signals::ControlModeValue::MotionMagicDutyCycle:
          case ctre::phoenix6::signals::ControlModeValue::PositionDutyCycleFOC:
          case ctre::phoenix6::signals::ControlModeValue::VelocityDutyCycleFOC:
          case ctre::phoenix6::signals::ControlModeValue::MotionMagicDutyCycleFOC:
          case ctre::phoenix6::signals::ControlModeValue::PositionVoltage:
          case ctre::phoenix6::signals::ControlModeValue::VelocityVoltage:
          case ctre::phoenix6::signals::ControlModeValue::MotionMagicVoltage:
          case ctre::phoenix6::signals::ControlModeValue::PositionVoltageFOC:
          case ctre::phoenix6::signals::ControlModeValue::VelocityVoltageFOC:
          case ctre::phoenix6::signals::ControlModeValue::MotionMagicVoltageFOC:
          case ctre::phoenix6::signals::ControlModeValue::PositionTorqueCurrentFOC:
          case ctre::phoenix6::signals::ControlModeValue::VelocityTorqueCurrentFOC:
          case ctre::phoenix6::signals::ControlModeValue::MotionMagicTorqueCurrentFOC:
          case ctre::phoenix6::signals::ControlModeValue::MotionMagicVelocityDutyCycle:
          case ctre::phoenix6::signals::ControlModeValue::MotionMagicVelocityDutyCycleFOC:
          case ctre::phoenix6::signals::ControlModeValue::MotionMagicVelocityVoltage:
          case ctre::phoenix6::signals::ControlModeValue::MotionMagicVelocityVoltageFOC:
          case ctre::phoenix6::signals::ControlModeValue::MotionMagicVelocityTorqueCurrentFOC:
          case ctre::phoenix6::signals::ControlModeValue::MotionMagicExpoDutyCycle:
          case ctre::phoenix6::signals::ControlModeValue::MotionMagicExpoDutyCycleFOC:
          case ctre::phoenix6::signals::ControlModeValue::MotionMagicExpoVoltage:
          case ctre::phoenix6::signals::ControlModeValue::MotionMagicExpoVoltageFOC:
          case ctre::phoenix6::signals::ControlModeValue::MotionMagicExpoTorqueCurrentFOC:
            setpoints.push_back(motor->GetClosedLoopReference().GetValue() * m_sensorConversions.setpoint);
            errors.push_back(motor->GetClosedLoopError().GetValue() * m_sensorConversions.setpoint);
            break;
          default:
            setpoints.push_back(NAN);
            errors.push_back(NAN);
        }
        positions.push_back(motor->GetPosition().GetValue().to<double>() * m_sensorConversions.position);
        velocities.push_back(motor->GetVelocity().GetValue().to<double>() * m_sensorConversions.velocity);
        outputs.push_back(motor->GetDutyCycle().GetValue().to<double>());
      }
      m_pntTable->PutNumberArray("status/setpoints", setpoints);
      m_pntTable->PutNumberArray("status/positions", positions);
      m_pntTable->PutNumberArray("status/velocities", velocities);
      m_pntTable->PutNumberArray("status/outputs", outputs);
      m_pntTable->PutNumberArray("status/errors", errors);
    }
  }
}
```



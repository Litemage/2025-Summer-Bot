

# File talonsrx\_config.h

[**File List**](files.md) **>** [**argos\_lib**](dir_f9cbf5730473812e84551a5945ef39f8.md) **>** [**include**](dir_0330651415bf66743a1cd99e3d0db0bc.md) **>** [**argos\_lib**](dir_934baf9e7d2bb4710ca41f9f25ef3ea4.md) **>** [**config**](dir_297090c629331b6211a5a9bae4ee7118.md) **>** [**talonsrx\_config.h**](talonsrx__config_8h.md)

[Go to the documentation of this file](talonsrx__config_8h.md)


```C++


#pragma once

#include <ctre/phoenix/motorcontrol/can/TalonSRX.h>
#include <units/current.h>
#include <units/time.h>
#include <units/voltage.h>

#include "argos_lib/config/config_types.h"
#include "compile_time_member_check.h"
#include "status_frame_config.h"

namespace argos_lib {
  namespace talonsrx_config {
    HAS_MEMBER(inverted)
    HAS_MEMBER(neutralMode)
    HAS_MEMBER(pid0_allowableError)
    HAS_MEMBER(pid0_iZone)
    HAS_MEMBER(pid0_kD)
    HAS_MEMBER(pid0_kF)
    HAS_MEMBER(pid0_kI)
    HAS_MEMBER(pid0_kP)
    HAS_MEMBER(pid0_selectedSensor)
    HAS_MEMBER(remoteFilter0_addr)
    HAS_MEMBER(remoteFilter0_type)
    HAS_MEMBER(sensorPhase)
    HAS_MEMBER(voltCompSat)
    HAS_MEMBER(statusFrameMotorMode)
    HAS_MEMBER(peakCurrentLimit)
    HAS_MEMBER(peakCurrentDuration)
    HAS_MEMBER(continuousCurrentLimit)
    HAS_MEMBER(peakOutputForward)
    HAS_MEMBER(peakOutputReverse)
    HAS_MEMBER(forwardLimitSwitchSource)
    HAS_MEMBER(reverseLimitSwitchSource)
    HAS_MEMBER(forwardLimitSwitchNormal)
    HAS_MEMBER(reverseLimitSwitchNormal)
    template <typename T>
    bool TalonSRXConfig(ctre::phoenix::motorcontrol::can::TalonSRX& motorController,
                        units::millisecond_t configTimeout) {
      ctre::phoenix::motorcontrol::can::TalonSRXConfiguration config;
      auto timeout = configTimeout.to<int>();

      if constexpr (has_inverted<T>{}) {
        motorController.SetInverted(T::inverted);
      }
      if constexpr (has_sensorPhase<T>{}) {
        motorController.SetSensorPhase(T::sensorPhase);
      }
      if constexpr (has_neutralMode<T>{}) {
        motorController.SetNeutralMode(T::neutralMode);
      }
      if constexpr (has_voltCompSat<T>{}) {
        constexpr units::volt_t voltage = T::voltCompSat;
        config.voltageCompSaturation = voltage.to<double>();
        motorController.EnableVoltageCompensation(true);
      } else {
        motorController.EnableVoltageCompensation(false);
      }
      if constexpr (has_remoteFilter0_addr<T>{} && has_remoteFilter0_type<T>{}) {
        ctre::phoenix::motorcontrol::can::FilterConfiguration filterConfig;
        filterConfig.remoteSensorDeviceID = T::remoteFilter0_addr.address;
        filterConfig.remoteSensorSource = T::remoteFilter0_type;
        config.remoteFilter0 = filterConfig;
      }
      if constexpr (has_pid0_selectedSensor<T>{}) {
        config.primaryPID.selectedFeedbackSensor = T::pid0_selectedSensor;
      }
      if constexpr (has_pid0_kP<T>{}) {
        config.slot0.kP = T::pid0_kP;
      }
      if constexpr (has_pid0_kI<T>{}) {
        config.slot0.kI = T::pid0_kI;
      }
      if constexpr (has_pid0_kD<T>{}) {
        config.slot0.kD = T::pid0_kD;
      }
      if constexpr (has_pid0_kF<T>{}) {
        config.slot0.kF = T::pid0_kF;
      }
      if constexpr (has_pid0_iZone<T>{}) {
        config.slot0.integralZone = T::pid0_iZone;
      }
      if constexpr (has_pid0_allowableError<T>{}) {
        config.slot0.allowableClosedloopError = T::pid0_allowableError;
      }
      if constexpr (has_peakCurrentLimit<T>()) {
        constexpr units::ampere_t currentLimit = T::peakCurrentLimit;
        static_assert(currentLimit.to<double>() > 0, "Current limit must be positive");
        config.peakCurrentLimit = std::round(currentLimit.to<double>());
      }
      if constexpr (has_peakCurrentDuration<T>()) {
        constexpr units::millisecond_t currentDuration = T::peakCurrentDuration;
        static_assert(currentDuration.to<double>() > 0, "Current duration must be positive");
        config.peakCurrentDuration = std::round(currentDuration.to<double>());
      }
      if constexpr (has_continuousCurrentLimit<T>()) {
        constexpr units::ampere_t currentLimit = T::continuousCurrentLimit;
        static_assert(currentLimit.to<double>() > 0, "Current limit must be positive");
        config.continuousCurrentLimit = std::round(currentLimit.to<double>());
      }
      if constexpr (has_peakOutputForward<T>()) {
        config.peakOutputForward = T::peakOutputForward;
      }
      if constexpr (has_peakOutputReverse<T>()) {
        config.peakOutputReverse = T::peakOutputReverse;
      }

      if constexpr (has_statusFrameMotorMode<T>()) {
        argos_lib::status_frame_config::SetMotorStatusFrameRates(motorController, T::statusFrameMotorMode);
      }

      if constexpr (has_forwardLimitSwitchSource<T>()) {
        config.forwardLimitSwitchSource = T::forwardLimitSwitchSource;
      }

      if constexpr (has_reverseLimitSwitchSource<T>()) {
        config.reverseLimitSwitchSource = T::reverseLimitSwitchSource;
      }

      if constexpr (has_forwardLimitSwitchNormal<T>()) {
        config.forwardLimitSwitchNormal = T::forwardLimitSwitchNormal;
      }

      if constexpr (has_reverseLimitSwitchNormal<T>()) {
        config.reverseLimitSwitchNormal = T::reverseLimitSwitchNormal;
      }

      // enable current limiting if any current limiting option is set, disable if none are
      if (has_continuousCurrentLimit<T>() || has_peakCurrentLimit<T>() || has_peakCurrentDuration<T>()) {
        motorController.EnableCurrentLimit(true);
      } else {
        motorController.EnableCurrentLimit(false);
      }

      // ensure using single threshold if peakCurrentLimit is not set but continuousCurrentLimit is
      if (!has_peakCurrentLimit<T>() && has_continuousCurrentLimit<T>()) {
        config.peakCurrentLimit = 0;
      }

      return 0 != motorController.ConfigAllSettings(config, timeout);
    }

    template <typename CompetitionConfig, typename PracticeConfig>
    bool TalonSRXConfig(ctre::phoenix::motorcontrol::can::TalonSRX& motorController,
                        units::millisecond_t configTimeout,
                        argos_lib::RobotInstance instance) {
      switch (instance) {
        case argos_lib::RobotInstance::Competition:
          return TalonSRXConfig<CompetitionConfig>(motorController, configTimeout);
          break;
        case argos_lib::RobotInstance::Practice:
          return TalonSRXConfig<PracticeConfig>(motorController, configTimeout);
          break;
      }
      return false;
    }

  }  // namespace talonsrx_config
}  // namespace argos_lib
```



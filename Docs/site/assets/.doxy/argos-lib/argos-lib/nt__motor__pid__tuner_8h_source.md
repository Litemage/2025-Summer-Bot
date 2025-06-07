

# File nt\_motor\_pid\_tuner.h

[**File List**](files.md) **>** [**argos\_lib**](dir_f9cbf5730473812e84551a5945ef39f8.md) **>** [**include**](dir_0330651415bf66743a1cd99e3d0db0bc.md) **>** [**argos\_lib**](dir_934baf9e7d2bb4710ca41f9f25ef3ea4.md) **>** [**general**](dir_ce90de3a31c0930a75a0088390301e44.md) **>** [**nt\_motor\_pid\_tuner.h**](nt__motor__pid__tuner_8h.md)

[Go to the documentation of this file](nt__motor__pid__tuner_8h.md)


```C++


#pragma once

#include <condition_variable>
#include <initializer_list>
#include <memory>
#include <mutex>
#include <string>
#include <thread>
#include <vector>

#include <ctre/phoenix6/core/CoreTalonFX.hpp>

#include "argos_lib/general/nt_subscriber.h"

namespace argos_lib {

  template <class Callable>
  constexpr double GetPositionConversionFactor(Callable toPhysicalUnitsFunction) {
    return toPhysicalUnitsFunction(units::angle::turn_t{1}).template to<double>();
  }

  template <class Callable>
  constexpr double GetVelocityConversionFactor(Callable toPhysicalUnitsFunction) {
    return toPhysicalUnitsFunction(units::angle::turn_t{1.0} / units::time::second_t{1.0}).template to<double>();
  }

  struct ClosedLoopSensorConversions {
    double position{1.0};  
    double velocity{1.0};  
    double setpoint{
        1.0};  
  };

  class NTMotorPIDTuner {
    using BaseTalon = ctre::phoenix6::hardware::core::CoreTalonFX;

   public:
    NTMotorPIDTuner(const std::string& tableName,
                    std::initializer_list<BaseTalon*> motors,
                    unsigned pidSlot,
                    ClosedLoopSensorConversions sensorConversions = {});

    ~NTMotorPIDTuner();

   private:
    argos_lib::NTSubscriber
        m_updateSubscriber;  
    const std::vector<BaseTalon*> m_pMotors;       
    const unsigned m_pidSlot;                      
    std::shared_ptr<nt::NetworkTable> m_pntTable;  
    ClosedLoopSensorConversions
        m_sensorConversions;  

    std::mutex m_threadMutex;                
    std::condition_variable m_threadStopCv;  
    std::thread m_statusUpdateThread;        

    ctre::phoenix6::configs::SlotConfigs m_activeConfigs;  

    void UpdateClosedLoopMonitoringThread();
  };

}  // namespace argos_lib
```





# File cancoder\_config.h

[**File List**](files.md) **>** [**argos\_lib**](dir_f9cbf5730473812e84551a5945ef39f8.md) **>** [**include**](dir_0330651415bf66743a1cd99e3d0db0bc.md) **>** [**argos\_lib**](dir_934baf9e7d2bb4710ca41f9f25ef3ea4.md) **>** [**config**](dir_297090c629331b6211a5a9bae4ee7118.md) **>** [**cancoder\_config.h**](cancoder__config_8h.md)

[Go to the documentation of this file](cancoder__config_8h.md)


```C++


#pragma once

#include <units/time.h>

#include <ctre/phoenix6/CANcoder.hpp>

#include "compile_time_member_check.h"

namespace argos_lib {
  namespace cancoder_config {
    using CANcoder = ctre::phoenix6::hardware::CANcoder;

    HAS_MEMBER(direction)
    HAS_MEMBER(magOffset)
    HAS_MEMBER(absoluteSensorDiscontinuityPoint)

    
    template <typename T>
    bool CanCoderConfig(CANcoder& encoder, units::millisecond_t configTimeout) {
      ctre::phoenix6::configs::CANcoderConfiguration config;
      encoder.GetConfigurator().Refresh(config.MagnetSensor, configTimeout);

      if constexpr (has_direction<T>{}) {
        config.MagnetSensor.SensorDirection = T::direction;
      }
      if constexpr (has_absoluteSensorDiscontinuityPoint<T>{}) {
        config.MagnetSensor.AbsoluteSensorDiscontinuityPoint = T::absoluteSensorDiscontinuityPoint;
      }
      if constexpr (has_magOffset<T>{}) {
        config.MagnetSensor.WithMagnetOffset = T::magOffset;
      }

      return ctre::phoenix::StatusCode::OK == encoder.GetConfigurator().Apply(config, configTimeout);
    }

    template <typename CompetitionConfig, typename PracticeConfig>
    bool CanCoderConfig(CANcoder& encoder, units::millisecond_t configTimeout, argos_lib::RobotInstance instance) {
      switch (instance) {
        case argos_lib::RobotInstance::Competition:
          return CanCoderConfig<CompetitionConfig>(encoder, configTimeout);
          break;
        case argos_lib::RobotInstance::Practice:
          return CanCoderConfig<PracticeConfig>(encoder, configTimeout);
          break;
      }
      return false;
    }

  }  // namespace cancoder_config
}  // namespace argos_lib
```



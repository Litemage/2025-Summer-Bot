

# File swerve\_utils.h

[**File List**](files.md) **>** [**argos\_lib**](dir_f9cbf5730473812e84551a5945ef39f8.md) **>** [**include**](dir_0330651415bf66743a1cd99e3d0db0bc.md) **>** [**argos\_lib**](dir_934baf9e7d2bb4710ca41f9f25ef3ea4.md) **>** [**general**](dir_ce90de3a31c0930a75a0088390301e44.md) **>** [**swerve\_utils.h**](swerve__utils_8h.md)

[Go to the documentation of this file](swerve__utils_8h.md)


```C++


#pragma once

#include <frc/kinematics/SwerveModuleState.h>
#include <units/angle.h>
#include <units/angular_velocity.h>
#include <units/velocity.h>

#include <optional>

#include "interpolation.h"

namespace argos_lib {
  namespace swerve {

    frc::SwerveModuleState Optimize(frc::SwerveModuleState desiredState,
                                    units::degree_t currentModuleAngle,
                                    units::degrees_per_second_t currentModuleAngularRate,
                                    units::feet_per_second_t currentModuleDriveVel,
                                    units::feet_per_second_t maxVelocity);

    struct SwerveModulePositions {
      units::degree_t FrontLeft;
      units::degree_t FrontRight;
      units::degree_t RearRight;
      units::degree_t RearLeft;
    };

    struct TranslationSpeeds {
      double forwardSpeedPct;  
      double leftSpeedPct;     
    };

    template <class T>
    [[nodiscard]] constexpr TranslationSpeeds CircularInterpolate(const TranslationSpeeds rawSpeeds,
                                                                  const T interpMap) {
      const double magnitude = std::sqrt(std::pow(rawSpeeds.forwardSpeedPct, 2) + std::pow(rawSpeeds.leftSpeedPct, 2));
      const double angle = std::atan2(rawSpeeds.leftSpeedPct, rawSpeeds.forwardSpeedPct);
      const double mappedMagnitude = interpMap(magnitude);
      return TranslationSpeeds{mappedMagnitude * std::cos(angle), mappedMagnitude * std::sin(angle)};
    }

  }  // namespace swerve
}  // namespace argos_lib
```



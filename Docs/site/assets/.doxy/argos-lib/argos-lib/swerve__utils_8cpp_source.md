

# File swerve\_utils.cpp

[**File List**](files.md) **>** [**argos\_lib**](dir_f9cbf5730473812e84551a5945ef39f8.md) **>** [**cpp**](dir_cf4b00708d9639a2579b4441eb30ca52.md) **>** [**general**](dir_16b6c439f6536703101f25e459a4699b.md) **>** [**swerve\_utils.cpp**](swerve__utils_8cpp.md)

[Go to the documentation of this file](swerve__utils_8cpp.md)


```C++


#include "argos_lib/general/swerve_utils.h"

#include <cmath>

#include "argos_lib/general/angle_utils.h"

using argos_lib::angle::ConstrainAngle;
using argos_lib::angle::InvertedAngle;
using argos_lib::angle::NearestAngle;
using argos_lib::swerve::Optimize;

frc::SwerveModuleState argos_lib::swerve::Optimize(frc::SwerveModuleState desiredState,
                                                   units::degree_t currentModuleAngle,
                                                   units::degrees_per_second_t currentModuleAngularRate,
                                                   units::feet_per_second_t currentModuleDriveVel,
                                                   units::feet_per_second_t maxVelocity) {
  frc::SwerveModuleState closestForwardState{desiredState};
  frc::SwerveModuleState closestInverseState{desiredState};

  closestForwardState.angle = NearestAngle(desiredState.angle.Degrees(), currentModuleAngle);
  closestInverseState.angle = InvertedAngle(closestForwardState.angle.Degrees(), currentModuleAngle);
  closestInverseState.speed = closestInverseState.speed * -1.0;

  const auto fwdTurnSign = std::signbit((closestForwardState.angle.Degrees() - currentModuleAngle).to<double>());
  const auto revTurnSign = std::signbit((closestInverseState.angle.Degrees() - currentModuleAngle).to<double>());

  [[maybe_unused]] const auto velPreferFwd = currentModuleDriveVel > maxVelocity / 2;
  const auto velPreferRev = currentModuleDriveVel < -maxVelocity / 2;
  const auto angVelHasPreference = units::math::fabs(currentModuleAngularRate) > 20_deg_per_s;
  [[maybe_unused]] const auto angVelPreferFwd =
      angVelHasPreference && fwdTurnSign == std::signbit(currentModuleAngularRate.to<double>());
  const auto angVelPreferRev =
      angVelHasPreference && revTurnSign == std::signbit(currentModuleAngularRate.to<double>());

  const auto fwdDist = units::math::fabs(closestForwardState.angle.Degrees() - currentModuleAngle);
  const auto revDist = 180_deg - fwdDist;

  if (fwdDist < revDist && !(velPreferRev && angVelPreferRev)) {
    return closestForwardState;
  }
  return closestInverseState;
}
```



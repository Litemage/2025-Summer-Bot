

# File odometry\_aim.cpp

[**File List**](files.md) **>** [**argos\_lib**](dir_f9cbf5730473812e84551a5945ef39f8.md) **>** [**cpp**](dir_cf4b00708d9639a2579b4441eb30ca52.md) **>** [**general**](dir_16b6c439f6536703101f25e459a4699b.md) **>** [**odometry\_aim.cpp**](odometry__aim_8cpp.md)

[Go to the documentation of this file](odometry__aim_8cpp.md)


```C++


#include "argos_lib/general/odometry_aim.h"

#include <units/math.h>

#include <cmath>

units::degree_t argos_lib::odometry_aim::GetAngleToTarget(const frc::Translation2d& currentEstimatedRobotPose,
                                                          const frc::Translation3d& targetPoseOnField) {
  auto yawToTarget = units::math::atan2(targetPoseOnField.Y() - currentEstimatedRobotPose.Y(),
                                        targetPoseOnField.X() - currentEstimatedRobotPose.X());

  return 90.0_deg - yawToTarget;
}

units::meter_t argos_lib::odometry_aim::GetDistanceToTarget(const frc::Translation2d& currentEstimatedRobotPose,
                                                            const frc::Translation3d& targetPoseOnField) {
  auto Ydiff = targetPoseOnField.Y() - currentEstimatedRobotPose.Y();
  auto Xdiff = targetPoseOnField.X() - currentEstimatedRobotPose.X();
  return units::math::hypot(Ydiff, Xdiff);
}
```



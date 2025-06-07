

# File odometry\_aim.h

[**File List**](files.md) **>** [**argos\_lib**](dir_f9cbf5730473812e84551a5945ef39f8.md) **>** [**include**](dir_0330651415bf66743a1cd99e3d0db0bc.md) **>** [**argos\_lib**](dir_934baf9e7d2bb4710ca41f9f25ef3ea4.md) **>** [**general**](dir_ce90de3a31c0930a75a0088390301e44.md) **>** [**odometry\_aim.h**](odometry__aim_8h.md)

[Go to the documentation of this file](odometry__aim_8h.md)


```C++


#pragma once

#include <frc/geometry/Translation2d.h>
#include <frc/geometry/Translation3d.h>

#include "units/angle.h"
#include "units/length.h"

namespace argos_lib {
  namespace odometry_aim {
    units::degree_t GetAngleToTarget(const frc::Translation2d& currentEstimatedRobotPose,
                                     const frc::Translation3d& targetPoseOnField);

    units::meter_t GetDistanceToTarget(const frc::Translation2d& currentEstimatedRobotPose,
                                       const frc::Translation3d& targetPoseOnField);
  }  // namespace odometry_aim
}  // namespace argos_lib
```



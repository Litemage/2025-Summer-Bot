

# File geometry.h

[**File List**](files.md) **>** [**argos\_lib**](dir_f9cbf5730473812e84551a5945ef39f8.md) **>** [**include**](dir_0330651415bf66743a1cd99e3d0db0bc.md) **>** [**argos\_lib**](dir_934baf9e7d2bb4710ca41f9f25ef3ea4.md) **>** [**led**](dir_92b511606ba5c2da7e2dda655454d24f.md) **>** [**geometry.h**](geometry_8h.md)

[Go to the documentation of this file](geometry_8h.md)


```C++


#pragma once

#include <units/angle.h>

#include <optional>
#include <utility>

namespace argos_lib {
  namespace led {
    units::degree_t FlipHorizontal(units::degree_t incidentAngle);

    units::degree_t FlipVertical(units::degree_t inicidentAngle);

    bool PointInBox(float corner1X, float corner1Y, float corner2X, float corner2Y, float pointX, float pointY);

    std::optional<std::pair<float, float>> SegmentIntersection(
        float s1x1, float s1y1, float s1x2, float s1y2, float s2x1, float s2y1, float s2x2, float s2y2);
  }  // namespace led
}  // namespace argos_lib
```





# File angle\_utils.h

[**File List**](files.md) **>** [**argos\_lib**](dir_f9cbf5730473812e84551a5945ef39f8.md) **>** [**include**](dir_0330651415bf66743a1cd99e3d0db0bc.md) **>** [**argos\_lib**](dir_934baf9e7d2bb4710ca41f9f25ef3ea4.md) **>** [**general**](dir_ce90de3a31c0930a75a0088390301e44.md) **>** [**angle\_utils.h**](angle__utils_8h.md)

[Go to the documentation of this file](angle__utils_8h.md)


```C++


#pragma once

#include "units/angle.h"

namespace argos_lib {
  namespace angle {
    units::degree_t NearestAngle(units::degree_t desiredAngle, units::degree_t referenceAngle);

    units::degree_t InvertedAngle(units::degree_t desiredAngle, units::degree_t referenceAngle);

    units::degree_t ConstrainAngle(units::degree_t inVal, units::degree_t minVal, units::degree_t maxVal);
    double ConstrainAngle(double inVal, double minVal, double maxVal);
  }  // namespace angle
}  // namespace argos_lib
```





# File general.h

[**File List**](files.md) **>** [**argos\_lib**](dir_f9cbf5730473812e84551a5945ef39f8.md) **>** [**include**](dir_0330651415bf66743a1cd99e3d0db0bc.md) **>** [**argos\_lib**](dir_934baf9e7d2bb4710ca41f9f25ef3ea4.md) **>** [**general**](dir_ce90de3a31c0930a75a0088390301e44.md) **>** [**general.h**](general_8h.md)

[Go to the documentation of this file](general_8h.md)


```C++


#pragma once

namespace argos_lib {

  template <typename T>
  constexpr static bool InThreshold(const T value, const T target, const T threshold) {
    return value >= target - threshold && value <= target + threshold;
  }
}  // namespace argos_lib
```



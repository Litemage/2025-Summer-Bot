

# File debounce\_settings.h

[**File List**](files.md) **>** [**argos\_lib**](dir_f9cbf5730473812e84551a5945ef39f8.md) **>** [**include**](dir_0330651415bf66743a1cd99e3d0db0bc.md) **>** [**argos\_lib**](dir_934baf9e7d2bb4710ca41f9f25ef3ea4.md) **>** [**general**](dir_ce90de3a31c0930a75a0088390301e44.md) **>** [**debounce\_settings.h**](debounce__settings_8h.md)

[Go to the documentation of this file](debounce__settings_8h.md)


```C++


#pragma once

#include <units/time.h>

namespace argos_lib {

  struct DebounceSettings {
    units::millisecond_t activateTime;
    units::millisecond_t clearTime;
  };

}  // namespace argos_lib
```



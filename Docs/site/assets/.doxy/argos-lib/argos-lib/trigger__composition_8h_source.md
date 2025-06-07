

# File trigger\_composition.h

[**File List**](files.md) **>** [**argos\_lib**](dir_f9cbf5730473812e84551a5945ef39f8.md) **>** [**include**](dir_0330651415bf66743a1cd99e3d0db0bc.md) **>** [**argos\_lib**](dir_934baf9e7d2bb4710ca41f9f25ef3ea4.md) **>** [**controller**](dir_1b5ab51e1de305e693feb9e8d9da64c0.md) **>** [**trigger\_composition.h**](trigger__composition_8h.md)

[Go to the documentation of this file](trigger__composition_8h.md)


```C++


#pragma once

#include <frc2/command/button/Trigger.h>

#include <vector>

namespace argos_lib {
  namespace triggers {
    frc2::Trigger OneOf(std::vector<frc2::Trigger> triggers);

    frc2::Trigger NoneOf(std::vector<frc2::Trigger> triggers);

    frc2::Trigger AnyOf(std::vector<frc2::Trigger> triggers);

    frc2::Trigger AllOf(std::vector<frc2::Trigger> triggers);
  }  // namespace triggers
}  // namespace argos_lib
```



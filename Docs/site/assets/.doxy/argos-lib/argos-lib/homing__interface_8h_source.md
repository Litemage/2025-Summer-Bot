

# File homing\_interface.h

[**File List**](files.md) **>** [**argos\_lib**](dir_f9cbf5730473812e84551a5945ef39f8.md) **>** [**include**](dir_0330651415bf66743a1cd99e3d0db0bc.md) **>** [**argos\_lib**](dir_934baf9e7d2bb4710ca41f9f25ef3ea4.md) **>** [**homing**](dir_d41870077d9859a02d90bd74c6566322.md) **>** [**homing\_interface.h**](homing__interface_8h.md)

[Go to the documentation of this file](homing__interface_8h.md)


```C++


#pragma once

#include "argos_lib/general/swerve_utils.h"

namespace argos_lib {
  class SwerveHomeStorageInterface {
   public:
    virtual bool Save(const argos_lib::swerve::SwerveModulePositions& homePosition) = 0;

    [[nodiscard]] virtual std::optional<argos_lib::swerve::SwerveModulePositions> Load() = 0;
  };

  template <class T>
  class HomingStorageInterface {
   public:
    virtual bool Save(const T& homePosition) = 0;

    [[nodiscard]] virtual std::optional<T> Load() = 0;
  };

}  // namespace argos_lib
```



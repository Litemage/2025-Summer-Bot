

# File network\_tables\_homing\_storage.h

[**File List**](files.md) **>** [**argos\_lib**](dir_f9cbf5730473812e84551a5945ef39f8.md) **>** [**include**](dir_0330651415bf66743a1cd99e3d0db0bc.md) **>** [**argos\_lib**](dir_934baf9e7d2bb4710ca41f9f25ef3ea4.md) **>** [**homing**](dir_d41870077d9859a02d90bd74c6566322.md) **>** [**network\_tables\_homing\_storage.h**](network__tables__homing__storage_8h.md)

[Go to the documentation of this file](network__tables__homing__storage_8h.md)


```C++


#pragma once

#include <optional>
#include <string>

#include "argos_lib/general/swerve_utils.h"
#include "argos_lib/homing/homing_interface.h"

namespace argos_lib {
  namespace swerve {
    class NetworkTablesHomingStorage : public SwerveHomeStorageInterface {
     public:
      NetworkTablesHomingStorage(const std::string& tableName,
                                 const std::string& frontLeftPath,
                                 const std::string& frontRightPath,
                                 const std::string& rearRightPath,
                                 const std::string& rearLeftPath);

      bool Save(const argos_lib::swerve::SwerveModulePositions& homePosition) override;
      [[nodiscard]] std::optional<argos_lib::swerve::SwerveModulePositions> Load() override;

     private:
      const std::string m_tableName;
      const std::string m_frontLeftPath;
      const std::string m_frontRightPath;
      const std::string m_rearRightPath;
      const std::string m_rearLeftPath;
    };
  }  // namespace swerve
}  // namespace argos_lib
```



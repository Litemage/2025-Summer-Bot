

# File network\_tables\_homing\_storage.cpp

[**File List**](files.md) **>** [**argos\_lib**](dir_f9cbf5730473812e84551a5945ef39f8.md) **>** [**cpp**](dir_cf4b00708d9639a2579b4441eb30ca52.md) **>** [**homing**](dir_f3cbec9e965946ce7c914e3bb9c19088.md) **>** [**network\_tables\_homing\_storage.cpp**](network__tables__homing__storage_8cpp.md)

[Go to the documentation of this file](network__tables__homing__storage_8cpp.md)


```C++


#include "argos_lib/homing/network_tables_homing_storage.h"

#include <networktables/NetworkTableInstance.h>

using argos_lib::swerve::NetworkTablesHomingStorage;

NetworkTablesHomingStorage::NetworkTablesHomingStorage(const std::string& tableName,
                                                       const std::string& frontLeftPath,
                                                       const std::string& frontRightPath,
                                                       const std::string& rearRightPath,
                                                       const std::string& rearLeftPath)
    : m_tableName{tableName}
    , m_frontLeftPath{frontLeftPath}
    , m_frontRightPath{frontRightPath}
    , m_rearRightPath{rearRightPath}
    , m_rearLeftPath{rearLeftPath} {
  auto ntInstance{nt::NetworkTableInstance::GetDefault()};
  auto ntTable{ntInstance.GetTable(m_tableName)};
  ntTable->SetPersistent(m_frontLeftPath);
  ntTable->SetPersistent(m_frontRightPath);
  ntTable->SetPersistent(m_rearRightPath);
  ntTable->SetPersistent(m_rearLeftPath);
}

bool NetworkTablesHomingStorage::Save(const argos_lib::swerve::SwerveModulePositions& homePosition) {
  auto ntInstance{nt::NetworkTableInstance::GetDefault()};
  auto ntTable{ntInstance.GetTable(m_tableName)};

  ntTable->PutNumber(m_frontLeftPath, homePosition.FrontLeft.to<double>());
  ntTable->PutNumber(m_frontRightPath, homePosition.FrontRight.to<double>());
  ntTable->PutNumber(m_rearRightPath, homePosition.RearRight.to<double>());
  ntTable->PutNumber(m_rearLeftPath, homePosition.RearLeft.to<double>());

  return true;
}

std::optional<argos_lib::swerve::SwerveModulePositions> NetworkTablesHomingStorage::Load() {
  auto ntInstance{nt::NetworkTableInstance::GetDefault()};
  auto ntTable{ntInstance.GetTable(m_tableName)};
  // Read positions are in degrees
  return argos_lib::swerve::SwerveModulePositions{
      units::make_unit<units::degree_t>(ntTable->GetNumber(m_frontLeftPath, 0)),
      units::make_unit<units::degree_t>(ntTable->GetNumber(m_frontRightPath, 0)),
      units::make_unit<units::degree_t>(ntTable->GetNumber(m_rearRightPath, 0)),
      units::make_unit<units::degree_t>(ntTable->GetNumber(m_rearLeftPath, 0))};
}
```



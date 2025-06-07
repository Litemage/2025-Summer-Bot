

# File fs\_homing.cpp

[**File List**](files.md) **>** [**argos\_lib**](dir_f9cbf5730473812e84551a5945ef39f8.md) **>** [**cpp**](dir_cf4b00708d9639a2579b4441eb30ca52.md) **>** [**homing**](dir_f3cbec9e965946ce7c914e3bb9c19088.md) **>** [**fs\_homing.cpp**](fs__homing_8cpp.md)

[Go to the documentation of this file](fs__homing_8cpp.md)


```C++


#include "argos_lib/homing/fs_homing.h"

#include <cstdlib>
#include <fstream>
#include <iostream>

#include "wpi/fs.h"

using argos_lib::SwerveFSHomingStorage;

SwerveFSHomingStorage::SwerveFSHomingStorage(const fs::path& swerveHomesPath) : m_swerveHomesPath{swerveHomesPath} {}

bool SwerveFSHomingStorage::Save(const argos_lib::swerve::SwerveModulePositions& homePosition) {
  try {
    std::ofstream configFile(GetFilePath(), std::ios::out);
    configFile << homePosition.FrontLeft.to<double>() << ' ' << homePosition.FrontRight.to<double>() << ' '
               << homePosition.RearRight.to<double>() << ' ' << homePosition.RearLeft.to<double>();
    configFile.close();
    return true;
  } catch (...) {
    // Error accessing file
    std::cout << "[ERROR] Could not write to config file\n";
    return false;
  }
}

std::optional<argos_lib::swerve::SwerveModulePositions> SwerveFSHomingStorage::Load() {
  try {
    std::ifstream configFile(GetFilePath(), std::ios::in);
    double frontLeft, frontRight, rearRight, rearLeft;
    configFile >> frontLeft >> frontRight >> rearRight >> rearLeft;
    configFile.close();

    return argos_lib::swerve::SwerveModulePositions{{units::make_unit<units::degree_t>(frontLeft)},
                                                    {units::make_unit<units::degree_t>(frontRight)},
                                                    {units::make_unit<units::degree_t>(rearRight)},
                                                    {units::make_unit<units::degree_t>(rearLeft)}};
  } catch (...) {
    // Error accessing file
    std::cout << "[ERROR] Could not read from config file\n";
    return std::nullopt;
  }
}

fs::path SwerveFSHomingStorage::GetFilePath() {
  static const fs::path homeDir{"/home/lvuser"};
  static const fs::path configFile{homeDir / m_swerveHomesPath};

  // Create empty file if it doesn't exist yet
  if (!fs::exists(configFile)) {
    fs::create_directories(configFile.parent_path());
    std::ofstream newFile(configFile);
    newFile.close();
  }

  return configFile;
}
```



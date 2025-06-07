

# File fs\_homing.h

[**File List**](files.md) **>** [**argos\_lib**](dir_f9cbf5730473812e84551a5945ef39f8.md) **>** [**include**](dir_0330651415bf66743a1cd99e3d0db0bc.md) **>** [**argos\_lib**](dir_934baf9e7d2bb4710ca41f9f25ef3ea4.md) **>** [**homing**](dir_d41870077d9859a02d90bd74c6566322.md) **>** [**fs\_homing.h**](fs__homing_8h.md)

[Go to the documentation of this file](fs__homing_8h.md)


```C++


#pragma once

#include <fstream>
#include <iostream>

#include "argos_lib/general/swerve_utils.h"
#include "argos_lib/homing/homing_interface.h"
#include "units/base.h"
#include "wpi/fs.h"

namespace argos_lib {

  class SwerveFSHomingStorage : public SwerveHomeStorageInterface {
   public:
    explicit SwerveFSHomingStorage(const fs::path& swerveHomesPath);
    bool Save(const argos_lib::swerve::SwerveModulePositions& homePosition) override;
    std::optional<argos_lib::swerve::SwerveModulePositions> Load() override;

   private:
    fs::path GetFilePath();
    const fs::path m_swerveHomesPath;  
  };

  template <class T>
  class FSHomingStorage : public HomingStorageInterface<T> {
   public:
    explicit FSHomingStorage(const fs::path& homeFilePath) : m_homesPath{homeFilePath} {};

    bool Save(const T& homePosition) override {
      try {
        bool success = true;
        std::ofstream configFile(GetFilePath(), std::ios::out);
        if (configFile.good()) {
          configFile << homePosition.template to<double>();
          if (!configFile.good()) {
            std::cout << "[ERROR] Could not write to config file\n";
            success = false;
          }
        } else {
          std::cout << "[ERROR] Could not open config file\n";
          success = false;
        }
        configFile.close();
        return success;
      } catch (...) {
        // Error accessing file
        std::cout << "[ERROR] Could not write to config file\n";
        return false;
      }
    }

    std::optional<T> Load() override {
      try {
        bool success = true;
        std::ifstream configFile(GetFilePath(), std::ios::in);

        if (configFile.peek() == std::ifstream::traits_type::eof()) {
          return std::nullopt;
        }

        double homePosition;
        configFile >> homePosition;

        configFile.close();
        if (success) {
          return units::make_unit<T>(homePosition);
        } else {
          return std::nullopt;
        }
      } catch (...) {
        // Error accessing file
        std::cout << "[ERROR] Could not read from config file\n";
        return std::nullopt;
      }
    }

   private:
    fs::path GetFilePath() {
      static const fs::path homeDir{"/home/lvuser"};
      const fs::path configFile{homeDir / m_homesPath};

      std::cout << "############# Path: " << configFile << '\n';

      // Create empty file if it doesn't exist yet
      if (!fs::exists(configFile)) {
        fs::create_directories(configFile.parent_path());
        std::ofstream newFile(configFile);
        newFile.close();
      }

      return configFile;
    }

    const fs::path m_homesPath;
  };
}  // namespace argos_lib
```



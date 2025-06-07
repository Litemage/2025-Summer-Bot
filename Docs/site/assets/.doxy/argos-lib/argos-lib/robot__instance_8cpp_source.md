

# File robot\_instance.cpp

[**File List**](files.md) **>** [**argos\_lib**](dir_f9cbf5730473812e84551a5945ef39f8.md) **>** [**cpp**](dir_cf4b00708d9639a2579b4441eb30ca52.md) **>** [**config**](dir_525e741a02ecda31c2fb045f53a43d0c.md) **>** [**robot\_instance.cpp**](robot__instance_8cpp.md)

[Go to the documentation of this file](robot__instance_8cpp.md)


```C++


#include <fstream>
#include <iostream>

#include "argos_lib/config/config_types.h"
#include "wpi/fs.h"

argos_lib::RobotInstance argos_lib::GetRobotInstance() {
  static const fs::path instanceFilePath{"/home/lvuser/robotInstance"};
  try {
    std::ifstream instanceFile(instanceFilePath, std::ios::in);
    std::string instanceString;
    instanceFile >> instanceString;
    instanceFile.close();
    if (instanceString.rfind("Competition", 0) != std::string::npos) {
      return argos_lib::RobotInstance::Competition;
    }
    if (instanceString.rfind("Practice", 0) != std::string::npos) {
      return argos_lib::RobotInstance::Practice;
    }
  } catch (...) {
    // Error accessing file
  }
  // If load fails, return competition
  std::cout << "[ERROR] Could not read from instance file. Defaulting to competition instance.\n";
  return argos_lib::RobotInstance::Competition;
}
```



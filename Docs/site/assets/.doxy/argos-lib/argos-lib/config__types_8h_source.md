

# File config\_types.h

[**File List**](files.md) **>** [**argos\_lib**](dir_f9cbf5730473812e84551a5945ef39f8.md) **>** [**include**](dir_0330651415bf66743a1cd99e3d0db0bc.md) **>** [**argos\_lib**](dir_934baf9e7d2bb4710ca41f9f25ef3ea4.md) **>** [**config**](dir_297090c629331b6211a5a9bae4ee7118.md) **>** [**config\_types.h**](config__types_8h.md)

[Go to the documentation of this file](config__types_8h.md)


```C++


#pragma once

#include <string_view>

namespace argos_lib {
  enum struct RobotInstance {
    Competition,  
    Practice      
  };

  RobotInstance GetRobotInstance();

  struct CANAddress {
    int address;
    std::string_view busName;

    CANAddress() = delete;
    constexpr CANAddress(int address, const std::string_view& busName = "rio") : address(address), busName(busName) {}
  };

  static inline int GetCANAddr(const argos_lib::CANAddress& compAddress,
                               const argos_lib::CANAddress& practiceAddress,
                               argos_lib::RobotInstance instance) {
    return instance == argos_lib::RobotInstance::Competition ? compAddress.address : practiceAddress.address;
  }

  static inline std::string_view GetCANBus(const argos_lib::CANAddress& compAddress,
                                           const argos_lib::CANAddress& practiceAddress,
                                           argos_lib::RobotInstance instance) {
    return instance == argos_lib::RobotInstance::Competition ? compAddress.busName : practiceAddress.busName;
  }

}  // namespace argos_lib
```



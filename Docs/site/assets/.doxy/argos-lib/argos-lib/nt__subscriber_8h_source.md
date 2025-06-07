

# File nt\_subscriber.h

[**File List**](files.md) **>** [**argos\_lib**](dir_f9cbf5730473812e84551a5945ef39f8.md) **>** [**include**](dir_0330651415bf66743a1cd99e3d0db0bc.md) **>** [**argos\_lib**](dir_934baf9e7d2bb4710ca41f9f25ef3ea4.md) **>** [**general**](dir_ce90de3a31c0930a75a0088390301e44.md) **>** [**nt\_subscriber.h**](nt__subscriber_8h.md)

[Go to the documentation of this file](nt__subscriber_8h.md)


```C++


#pragma once

#include <networktables/DoubleTopic.h>
#include <networktables/NetworkTableInstance.h>

#include <string>
#include <vector>

namespace argos_lib {
  class NTSubscriber {
   public:
    explicit NTSubscriber(const std::string& tableName);

    ~NTSubscriber();

    void AddMonitor(const std::string& keyName,
                    std::function<void(double)> onUpdateCallback,
                    const double defaultValue = 0.0,
                    const bool forceUpdate = true);

   private:
    const std::string m_tableName;           
    std::vector<NT_Entry> m_ntEntries;       
    std::vector<NT_Listener> m_ntListeners;  
  };

}  // namespace argos_lib
```



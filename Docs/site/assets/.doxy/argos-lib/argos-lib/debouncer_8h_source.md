

# File debouncer.h

[**File List**](files.md) **>** [**argos\_lib**](dir_f9cbf5730473812e84551a5945ef39f8.md) **>** [**include**](dir_0330651415bf66743a1cd99e3d0db0bc.md) **>** [**argos\_lib**](dir_934baf9e7d2bb4710ca41f9f25ef3ea4.md) **>** [**general**](dir_ce90de3a31c0930a75a0088390301e44.md) **>** [**debouncer.h**](debouncer_8h.md)

[Go to the documentation of this file](debouncer_8h.md)


```C++


#pragma once

#include <chrono>

#include "argos_lib/general/debounce_settings.h"
#include "units/time.h"

namespace argos_lib {

  class Debouncer {
   public:
    explicit Debouncer(const argos_lib::DebounceSettings debounceSettings, bool initialValue = false);

    explicit Debouncer(const units::millisecond_t symmetricDebounceTime);

    [[nodiscard]] bool operator()(bool newVal);

    [[nodiscard]] bool GetRawStatus();

    [[nodiscard]] bool GetDebouncedStatus();

    void Reset(bool newVal);

   private:
    argos_lib::DebounceSettings m_debounceSettings;  
    bool m_rawStatus;                                
    bool m_debouncedStatus;                          
    std::chrono::time_point<std::chrono::steady_clock>
        m_debounceTransitionTime;  
  };

}  // namespace argos_lib
```



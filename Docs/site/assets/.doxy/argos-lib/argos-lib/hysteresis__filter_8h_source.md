

# File hysteresis\_filter.h

[**File List**](files.md) **>** [**argos\_lib**](dir_f9cbf5730473812e84551a5945ef39f8.md) **>** [**include**](dir_0330651415bf66743a1cd99e3d0db0bc.md) **>** [**argos\_lib**](dir_934baf9e7d2bb4710ca41f9f25ef3ea4.md) **>** [**general**](dir_ce90de3a31c0930a75a0088390301e44.md) **>** [**hysteresis\_filter.h**](hysteresis__filter_8h.md)

[Go to the documentation of this file](hysteresis__filter_8h.md)


```C++


#pragma once

namespace argos_lib {

  template <typename T>
  class HysteresisFilter {
   public:
    HysteresisFilter() = delete;

    HysteresisFilter(T deactivateThreshold, T activateThreshold)
        : m_activateThreshold(activateThreshold), m_deactivateThreshold(deactivateThreshold) {}

    [[nodiscard]] bool operator()(T newValue) {
      if (m_currentState) {
        if (newValue < m_deactivateThreshold) {
          m_currentState = false;
        }
      } else {
        if (newValue > m_activateThreshold) {
          m_currentState = true;
        }
      }
      return m_currentState;
    }

   private:
    const T m_activateThreshold;    
    const T m_deactivateThreshold;  
    bool m_currentState;            
  };
}  // namespace argos_lib
```



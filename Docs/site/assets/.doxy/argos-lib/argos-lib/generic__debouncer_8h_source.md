

# File generic\_debouncer.h

[**File List**](files.md) **>** [**argos\_lib**](dir_f9cbf5730473812e84551a5945ef39f8.md) **>** [**include**](dir_0330651415bf66743a1cd99e3d0db0bc.md) **>** [**argos\_lib**](dir_934baf9e7d2bb4710ca41f9f25ef3ea4.md) **>** [**general**](dir_ce90de3a31c0930a75a0088390301e44.md) **>** [**generic\_debouncer.h**](generic__debouncer_8h.md)

[Go to the documentation of this file](generic__debouncer_8h.md)


```C++


#pragma once

#include <units/time.h>

#include <chrono>

namespace argos_lib {
  template <class T>
  class GenericDebouncer {
   public:
    explicit GenericDebouncer(const units::millisecond_t symmetricDebounceTime, T initialValue = {})
        : m_debounceTime{symmetricDebounceTime}
        , m_rawStatus{initialValue}
        , m_debouncedStatus{initialValue}
        , m_debounceTransitionTime{std::chrono::steady_clock::now()} {}

    [[nodiscard]] T operator()(T newVal) {
      const auto prevRawValue = m_rawStatus;
      const auto curTime = std::chrono::steady_clock::now();

      if (newVal != m_debouncedStatus && newVal != prevRawValue) {
        m_debounceTransitionTime = curTime;
      }

      if (newVal != m_debouncedStatus) {
        const auto timeSinceTransition = units::millisecond_t{static_cast<double>(
            std::chrono::duration_cast<std::chrono::milliseconds>(curTime - m_debounceTransitionTime).count())};
        if (timeSinceTransition >= m_debounceTime) {
          m_debouncedStatus = newVal;
        }
      }

      m_rawStatus = newVal;
      return m_debouncedStatus;
    }

    void Reset(T newVal) {
      m_rawStatus = newVal;
      m_debouncedStatus = newVal;
    }

   private:
    units::millisecond_t m_debounceTime;
    T m_rawStatus;        
    T m_debouncedStatus;  
    std::chrono::time_point<std::chrono::steady_clock>
        m_debounceTransitionTime;  
  };

}  // namespace argos_lib
```



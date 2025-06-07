

# File debouncer.cpp

[**File List**](files.md) **>** [**argos\_lib**](dir_f9cbf5730473812e84551a5945ef39f8.md) **>** [**cpp**](dir_cf4b00708d9639a2579b4441eb30ca52.md) **>** [**general**](dir_16b6c439f6536703101f25e459a4699b.md) **>** [**debouncer.cpp**](debouncer_8cpp.md)

[Go to the documentation of this file](debouncer_8cpp.md)


```C++


#include "argos_lib/general/debouncer.h"

using argos_lib::Debouncer;

Debouncer::Debouncer(const argos_lib::DebounceSettings debounceSettings, bool initialValue)
    : m_debounceSettings{debounceSettings}
    , m_rawStatus{initialValue}
    , m_debouncedStatus{initialValue}
    , m_debounceTransitionTime{std::chrono::steady_clock::now()} {}

Debouncer::Debouncer(const units::millisecond_t symmetricDebounceTime)
    : Debouncer{argos_lib::DebounceSettings{symmetricDebounceTime, symmetricDebounceTime}} {}

[[nodiscard]] bool Debouncer::operator()(bool newVal) {
  const auto prevRawValue = m_rawStatus;
  const auto curTime = std::chrono::steady_clock::now();

  if (prevRawValue == m_debouncedStatus && newVal != m_debouncedStatus) {
    m_debounceTransitionTime = curTime;
  }

  if (newVal != m_debouncedStatus) {
    const auto timeSinceTransition = units::millisecond_t{static_cast<double>(
        std::chrono::duration_cast<std::chrono::milliseconds>(curTime - m_debounceTransitionTime).count())};
    if (newVal) {
      if (timeSinceTransition >= m_debounceSettings.activateTime) {
        m_debouncedStatus = newVal;
      }
    } else {
      if (timeSinceTransition >= m_debounceSettings.clearTime) {
        m_debouncedStatus = newVal;
      }
    }
  }

  m_rawStatus = newVal;
  return m_debouncedStatus;
}

bool Debouncer::GetRawStatus() {
  return m_rawStatus;
}

bool Debouncer::GetDebouncedStatus() {
  return m_debouncedStatus;
}

void Debouncer::Reset(bool newVal) {
  m_rawStatus = newVal;
  m_debouncedStatus = newVal;
}
```



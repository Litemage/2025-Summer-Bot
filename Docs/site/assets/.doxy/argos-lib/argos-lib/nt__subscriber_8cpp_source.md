

# File nt\_subscriber.cpp

[**File List**](files.md) **>** [**argos\_lib**](dir_f9cbf5730473812e84551a5945ef39f8.md) **>** [**cpp**](dir_cf4b00708d9639a2579b4441eb30ca52.md) **>** [**general**](dir_16b6c439f6536703101f25e459a4699b.md) **>** [**nt\_subscriber.cpp**](nt__subscriber_8cpp.md)

[Go to the documentation of this file](nt__subscriber_8cpp.md)


```C++


#include "argos_lib/general/nt_subscriber.h"

#include <networktables/DoubleTopic.h>
#include <networktables/NetworkTable.h>
#include <networktables/NetworkTableInstance.h>

#include "fmt/format.h"

using argos_lib::NTSubscriber;

NTSubscriber::NTSubscriber(const std::string& tableName) : m_tableName{tableName} {}

NTSubscriber::~NTSubscriber() {
  // Need to release all handles
  for (auto listenerIt = m_ntListeners.begin(); listenerIt != m_ntListeners.end(); ++listenerIt) {
    nt::RemoveListener(*listenerIt);
  }
  for (auto entryIt = m_ntEntries.begin(); entryIt != m_ntEntries.end(); ++entryIt) {
    nt::ReleaseEntry(*entryIt);
  }
}

void NTSubscriber::AddMonitor(const std::string& keyName,
                              std::function<void(double)> onUpdateCallback,
                              const double defaultValue,
                              const bool forceUpdate) {
  NT_Topic topic = nt::GetTopic(NT_GetDefaultInstance(), fmt::format("{}/{}", m_tableName, keyName));
  m_ntEntries.push_back(nt::GetEntry(topic, NT_DOUBLE, "double"));
  if (forceUpdate) {
    nt::SetDouble(m_ntEntries.back(), defaultValue);
  } else {
    nt::SetDefaultDouble(m_ntEntries.back(), defaultValue);
  }

  nt::AddListener(m_ntEntries.back(), nt::EventFlags::kValueAll, [onUpdateCallback](const nt::Event& e) {
    onUpdateCallback(e.GetValueEventData()->value.GetDouble());
  });
}
```



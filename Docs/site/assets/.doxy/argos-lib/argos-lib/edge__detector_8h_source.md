

# File edge\_detector.h

[**File List**](files.md) **>** [**argos\_lib**](dir_f9cbf5730473812e84551a5945ef39f8.md) **>** [**include**](dir_0330651415bf66743a1cd99e3d0db0bc.md) **>** [**argos\_lib**](dir_934baf9e7d2bb4710ca41f9f25ef3ea4.md) **>** [**general**](dir_ce90de3a31c0930a75a0088390301e44.md) **>** [**edge\_detector.h**](edge__detector_8h.md)

[Go to the documentation of this file](edge__detector_8h.md)


```C++


#pragma once

#include <string>

namespace argos_lib {

  class EdgeDetector {
   public:
    enum class EdgeDetectSettings { DETECT_BOTH, DETECT_FALLING, DETECT_RISING };

    enum class edgeStatus { FALLING, RISING, ERROR, NONE };

    explicit EdgeDetector(EdgeDetector::EdgeDetectSettings _settings, bool initialValue = false);

    bool operator()(bool curVal);

    edgeStatus Calculate(bool curVal);

    std::string ToString(edgeStatus status);

   private:
    EdgeDetector::EdgeDetectSettings m_settings;

    bool m_previousValue;

    edgeStatus DetectFalling(bool currentValue);

    edgeStatus DetectRising(bool currentValue);
  };
}  // namespace argos_lib
```



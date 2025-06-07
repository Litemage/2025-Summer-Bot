

# File edge\_detector.cpp

[**File List**](files.md) **>** [**argos\_lib**](dir_f9cbf5730473812e84551a5945ef39f8.md) **>** [**cpp**](dir_cf4b00708d9639a2579b4441eb30ca52.md) **>** [**general**](dir_16b6c439f6536703101f25e459a4699b.md) **>** [**edge\_detector.cpp**](edge__detector_8cpp.md)

[Go to the documentation of this file](edge__detector_8cpp.md)


```C++


#include "argos_lib/general/edge_detector.h"

#include "frc/smartdashboard/SmartDashboard.h"

using argos_lib::EdgeDetector;

EdgeDetector::EdgeDetector(EdgeDetector::EdgeDetectSettings _settings, bool initialValue) {
  m_settings = _settings;
  m_previousValue = initialValue;
}

bool EdgeDetector::operator()(bool curVal) {
  edgeStatus stat = Calculate(curVal);
  switch (m_settings) {
    case EdgeDetectSettings::DETECT_BOTH:
      return (stat == edgeStatus::RISING || stat == edgeStatus::FALLING);
      break;
    case EdgeDetectSettings::DETECT_RISING:
      return (stat == edgeStatus::RISING);
      break;
    case EdgeDetectSettings::DETECT_FALLING:
      return (stat == edgeStatus::FALLING);
      break;
  }
  return false;
}

EdgeDetector::edgeStatus EdgeDetector::Calculate(bool curVal) {
  edgeStatus statusReturn = edgeStatus::NONE;
  switch (m_settings) {
    case EdgeDetectSettings::DETECT_BOTH:
      if (DetectFalling(curVal) == edgeStatus::FALLING) {
        statusReturn = edgeStatus::FALLING;
      } else if (DetectRising(curVal) == edgeStatus::RISING) {
        statusReturn = edgeStatus::RISING;
      }
      break;
    case EdgeDetectSettings::DETECT_FALLING:
      statusReturn = DetectFalling(curVal);
      break;
    case EdgeDetectSettings::DETECT_RISING:
      statusReturn = DetectRising(curVal);
      break;
  }
  m_previousValue = curVal;
  return statusReturn;
}

std::string EdgeDetector::ToString(edgeStatus status) {
  switch (status) {
    case edgeStatus::RISING:
      return "Rising";
      break;
    case edgeStatus::FALLING:
      return "Falling";
      break;
    case edgeStatus::NONE:
      return "None";
      break;
    case edgeStatus::ERROR:
      return "Error";
      break;

    default:
      return "DEFAULT";
      break;
  }
}

EdgeDetector::edgeStatus EdgeDetector::DetectFalling(bool currentValue) {
  if (m_previousValue && !currentValue) {
    return edgeStatus::FALLING;
  } else {
    return edgeStatus::NONE;
  }
}

EdgeDetector::edgeStatus EdgeDetector::DetectRising(bool currentValue) {
  if (!m_previousValue && currentValue) {
    return edgeStatus::RISING;
  } else {
    return edgeStatus::NONE;
  }
}
```



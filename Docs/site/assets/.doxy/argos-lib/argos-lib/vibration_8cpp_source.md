

# File vibration.cpp

[**File List**](files.md) **>** [**argos\_lib**](dir_f9cbf5730473812e84551a5945ef39f8.md) **>** [**cpp**](dir_cf4b00708d9639a2579b4441eb30ca52.md) **>** [**controller**](dir_449ae403f63c24360f06e13a33b5f84a.md) **>** [**vibration.cpp**](vibration_8cpp.md)

[Go to the documentation of this file](vibration_8cpp.md)


```C++


#include "argos_lib/controller/vibration.h"

#include <chrono>
#include <numbers>

using namespace argos_lib;

VibrationModel argos_lib::VibrationOff() {
  return []() { return VibrationStatus{0.0, 0.0}; };
}

VibrationModel argos_lib::VibrationConstant(double intensity) {
  return [intensity]() { return VibrationStatus{intensity, intensity}; };
}

VibrationModel argos_lib::VibrationConstant(double intensityLeft, double intensityRight) {
  return [intensityLeft, intensityRight]() { return VibrationStatus{intensityLeft, intensityRight}; };
}

VibrationModel argos_lib::VibrationSyncPulse(units::millisecond_t pulsePeriod,
                                             double intensityOn,
                                             double intensityOff) {
  auto msPeriod = pulsePeriod.to<int>();
  return [msPeriod, intensityOn, intensityOff]() {
    const auto periodTime =
        std::chrono::duration_cast<std::chrono::milliseconds>(std::chrono::steady_clock::now().time_since_epoch())
            .count() %
        msPeriod;
    const auto vibrationIntensity = periodTime < (msPeriod / 2) ? intensityOn : intensityOff;
    return VibrationStatus{vibrationIntensity, vibrationIntensity};
  };
}

VibrationModel argos_lib::VibrationAlternatePulse(units::millisecond_t pulsePeriod,
                                                  double intensityOn,
                                                  double intensityOff) {
  auto msPeriod = pulsePeriod.to<int>();
  return [msPeriod, intensityOn, intensityOff]() {
    const auto periodTime =
        std::chrono::duration_cast<std::chrono::milliseconds>(std::chrono::steady_clock::now().time_since_epoch())
            .count() %
        msPeriod;
    const auto vibrationState = periodTime < (msPeriod / 2);
    return VibrationStatus{vibrationState ? intensityOn : intensityOff, vibrationState ? intensityOff : intensityOn};
  };
}

VibrationModel argos_lib::VibrationSyncWave(units::millisecond_t pulsePeriod, double intensityOn, double intensityOff) {
  auto msPeriod = pulsePeriod.to<int>();
  return [msPeriod, intensityOn, intensityOff]() {
    const auto periodTime =
        std::chrono::duration_cast<std::chrono::milliseconds>(std::chrono::steady_clock::now().time_since_epoch())
            .count() %
        msPeriod;
    const auto periodProgress = static_cast<double>(periodTime) / msPeriod;
    const auto vibrationIntensity = std::cos(std::numbers::pi * 2.0 * periodProgress) / 2 + 0.5;
    const auto outputIntensity = intensityOff + vibrationIntensity * (intensityOn - intensityOff);
    return VibrationStatus{outputIntensity, outputIntensity};
  };
}

VibrationModel argos_lib::VibrationAlternateWave(units::millisecond_t pulsePeriod,
                                                 double intensityOn,
                                                 double intensityOff) {
  auto msPeriod = pulsePeriod.to<int>();
  return [msPeriod, intensityOn, intensityOff]() {
    const auto periodTime =
        std::chrono::duration_cast<std::chrono::milliseconds>(std::chrono::steady_clock::now().time_since_epoch())
            .count() %
        msPeriod;
    const auto periodProgress = static_cast<double>(periodTime) / msPeriod;
    const auto vibrationIntensityLeft = std::cos(std::numbers::pi * 2.0 * periodProgress) / 2 + 0.5;
    const auto vibrationIntensityRight = 1.0 - vibrationIntensityLeft;
    return VibrationStatus{intensityOff + vibrationIntensityLeft * (intensityOn - intensityOff),
                           intensityOff + vibrationIntensityRight * (intensityOn - intensityOff)};
  };
}

VibrationModel argos_lib::TemporaryVibrationPattern(argos_lib::VibrationModel temporaryModel,
                                                    units::millisecond_t temporaryModelDuration,
                                                    argos_lib::VibrationModel lastingModel) {
  auto startTime = std::chrono::steady_clock::now();
  return [startTime, temporaryModel, lastingModel, temporaryModelDuration]() {
    const units::millisecond_t duration{std::chrono::steady_clock::now() - startTime};
    if (duration > temporaryModelDuration) {
      return lastingModel();
    } else {
      return temporaryModel();
    }
  };
}
```



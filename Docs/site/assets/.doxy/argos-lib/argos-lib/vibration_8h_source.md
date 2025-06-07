

# File vibration.h

[**File List**](files.md) **>** [**argos\_lib**](dir_f9cbf5730473812e84551a5945ef39f8.md) **>** [**include**](dir_0330651415bf66743a1cd99e3d0db0bc.md) **>** [**argos\_lib**](dir_934baf9e7d2bb4710ca41f9f25ef3ea4.md) **>** [**controller**](dir_1b5ab51e1de305e693feb9e8d9da64c0.md) **>** [**vibration.h**](vibration_8h.md)

[Go to the documentation of this file](vibration_8h.md)


```C++


#pragma once

#include <units/time.h>

#include <functional>

namespace argos_lib {

  struct VibrationStatus {
    double intensityLeft = 0.0;   
    double intensityRight = 0.0;  
  };

  using VibrationModel = std::function<VibrationStatus()>;

  VibrationModel VibrationOff();

  VibrationModel VibrationConstant(double intensity);

  VibrationModel VibrationConstant(double intensityLeft, double intensityRight);

  VibrationModel VibrationSyncPulse(units::millisecond_t pulsePeriod, double intensityOn, double intensityOff = 0.0);

  VibrationModel VibrationSyncWave(units::millisecond_t pulsePeriod, double intensityOn, double intensityOff = 0.0);

  VibrationModel VibrationAlternatePulse(units::millisecond_t pulsePeriod,
                                         double intensityOn,
                                         double intensityOff = 0.0);

  VibrationModel VibrationAlternateWave(units::millisecond_t pulsePeriod,
                                        double intensityOn,
                                        double intensityOff = 0.0);

  VibrationModel TemporaryVibrationPattern(VibrationModel temporaryModel,
                                           units::millisecond_t temporaryModelDuration,
                                           VibrationModel lastingModel = VibrationOff());

}  // namespace argos_lib
```



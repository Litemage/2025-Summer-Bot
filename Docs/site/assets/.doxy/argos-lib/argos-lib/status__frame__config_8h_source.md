

# File status\_frame\_config.h

[**File List**](files.md) **>** [**argos\_lib**](dir_f9cbf5730473812e84551a5945ef39f8.md) **>** [**include**](dir_0330651415bf66743a1cd99e3d0db0bc.md) **>** [**argos\_lib**](dir_934baf9e7d2bb4710ca41f9f25ef3ea4.md) **>** [**config**](dir_297090c629331b6211a5a9bae4ee7118.md) **>** [**status\_frame\_config.h**](status__frame__config_8h.md)

[Go to the documentation of this file](status__frame__config_8h.md)


```C++


#pragma once

#include <ctre/phoenix6/core/CoreTalonFX.hpp>

namespace argos_lib {
  namespace status_frame_config {
    using BaseTalon = ctre::phoenix6::hardware::core::CoreTalonFX;
    enum class MotorPresetMode {
      Basic,              
      BasicFX,            
      Leader,             
      LeaderFX,           
      Follower,           
      FollowerFX,         
      MotionProfiling,    
      MotionProfilingFX,  
      Tuning,             
      TuningFX            
    };

    void SetMotorStatusFrameRates(BaseTalon& motor, MotorPresetMode motorMode);
  }  // namespace status_frame_config
}  // namespace argos_lib
```



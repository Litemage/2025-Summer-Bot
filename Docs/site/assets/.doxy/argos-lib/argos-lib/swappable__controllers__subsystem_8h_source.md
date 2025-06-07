

# File swappable\_controllers\_subsystem.h

[**File List**](files.md) **>** [**argos\_lib**](dir_f9cbf5730473812e84551a5945ef39f8.md) **>** [**include**](dir_0330651415bf66743a1cd99e3d0db0bc.md) **>** [**argos\_lib**](dir_934baf9e7d2bb4710ca41f9f25ef3ea4.md) **>** [**subsystems**](dir_74a079771991058d11b5f8805d16e2a9.md) **>** [**swappable\_controllers\_subsystem.h**](swappable__controllers__subsystem_8h.md)

[Go to the documentation of this file](swappable__controllers__subsystem_8h.md)


```C++


#pragma once

#include <frc2/command/SubsystemBase.h>

#include "argos_lib/controller/xbox_controller.h"

namespace argos_lib {

  class SwappableControllersSubsystem : public frc2::SubsystemBase {
   public:
    SwappableControllersSubsystem() = delete;
    SwappableControllersSubsystem(int driverControllerPort, int operatorControllerPort);

    void Swap();

    argos_lib::XboxController& DriverController();
    argos_lib::XboxController& OperatorController();

    void Periodic() override;

    void VibrateAll(argos_lib::VibrationModel newModel);

   private:
    argos_lib::XboxController m_driverController;    
    argos_lib::XboxController m_operatorController;  
    bool m_swapped;                                  

    void UpdateVibration();
  };

}  // namespace argos_lib
```



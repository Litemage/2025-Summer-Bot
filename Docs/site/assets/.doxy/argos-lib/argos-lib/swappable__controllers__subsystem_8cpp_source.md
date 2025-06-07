

# File swappable\_controllers\_subsystem.cpp

[**File List**](files.md) **>** [**argos\_lib**](dir_f9cbf5730473812e84551a5945ef39f8.md) **>** [**cpp**](dir_cf4b00708d9639a2579b4441eb30ca52.md) **>** [**subsystems**](dir_0a6d697c01cca447b97a2967adff34af.md) **>** [**swappable\_controllers\_subsystem.cpp**](swappable__controllers__subsystem_8cpp.md)

[Go to the documentation of this file](swappable__controllers__subsystem_8cpp.md)


```C++


#include "argos_lib/subsystems/swappable_controllers_subsystem.h"

using namespace argos_lib;

SwappableControllersSubsystem::SwappableControllersSubsystem(int driverControllerPort, int operatorControllerPort)
    : m_driverController(driverControllerPort), m_operatorController(operatorControllerPort), m_swapped(false) {}

void SwappableControllersSubsystem::Swap() {
  m_driverController.SwapSettings(m_operatorController);
  m_swapped = !m_swapped;
}

XboxController& SwappableControllersSubsystem::DriverController() {
  return m_swapped ? m_operatorController : m_driverController;
}
XboxController& SwappableControllersSubsystem::OperatorController() {
  return m_swapped ? m_driverController : m_operatorController;
}

void SwappableControllersSubsystem::Periodic() {
  UpdateVibration();
}

void SwappableControllersSubsystem::VibrateAll(VibrationModel newModel) {
  m_driverController.SetVibration(newModel);
  m_operatorController.SetVibration(newModel);
}

void SwappableControllersSubsystem::UpdateVibration() {
  m_driverController.UpdateVibration();
  m_operatorController.UpdateVibration();
}
```



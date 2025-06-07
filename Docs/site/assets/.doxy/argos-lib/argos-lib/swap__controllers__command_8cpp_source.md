

# File swap\_controllers\_command.cpp

[**File List**](files.md) **>** [**argos\_lib**](dir_f9cbf5730473812e84551a5945ef39f8.md) **>** [**cpp**](dir_cf4b00708d9639a2579b4441eb30ca52.md) **>** [**commands**](dir_c0b6341bb1e7e644bbb52b58767c2e0d.md) **>** [**swap\_controllers\_command.cpp**](swap__controllers__command_8cpp.md)

[Go to the documentation of this file](swap__controllers__command_8cpp.md)


```C++


#include "argos_lib/commands/swap_controllers_command.h"

using namespace argos_lib;

SwapControllersCommand::SwapControllersCommand(SwappableControllersSubsystem* controllers)
    : m_pControllerSubsystem(controllers) {}

void SwapControllersCommand::Initialize() {
  m_pControllerSubsystem->VibrateAll(argos_lib::VibrationConstant(1));
}

void SwapControllersCommand::End(bool) {
  m_pControllerSubsystem->Swap();
  m_pControllerSubsystem->VibrateAll(argos_lib::VibrationOff());
}
```



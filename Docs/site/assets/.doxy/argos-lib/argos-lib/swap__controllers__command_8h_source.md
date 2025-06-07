

# File swap\_controllers\_command.h

[**File List**](files.md) **>** [**argos\_lib**](dir_f9cbf5730473812e84551a5945ef39f8.md) **>** [**include**](dir_0330651415bf66743a1cd99e3d0db0bc.md) **>** [**argos\_lib**](dir_934baf9e7d2bb4710ca41f9f25ef3ea4.md) **>** [**commands**](dir_b5b6a4436ac847838034b63997323b48.md) **>** [**swap\_controllers\_command.h**](swap__controllers__command_8h.md)

[Go to the documentation of this file](swap__controllers__command_8h.md)


```C++


#pragma once

#include <frc2/command/Command.h>
#include <frc2/command/CommandHelper.h>

#include "argos_lib/subsystems/swappable_controllers_subsystem.h"

namespace argos_lib {

  class SwapControllersCommand : public frc2::CommandHelper<frc2::Command, SwapControllersCommand> {
   public:
    explicit SwapControllersCommand(SwappableControllersSubsystem* controllers);

    void Initialize() override;

    void End(bool) override;

   private:
    SwappableControllersSubsystem* m_pControllerSubsystem;
  };

}  // namespace argos_lib
```



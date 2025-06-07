

# File Autos.cpp

[**File List**](files.md) **>** [**commands**](dir_936b7b8edf6aa316affdf0e21f6b0c34.md) **>** [**Autos.cpp**](_autos_8cpp.md)

[Go to the documentation of this file](_autos_8cpp.md)


```C++
// Copyright (c) FIRST and other WPILib contributors.
// Open Source Software; you can modify and/or share it under the terms of
// the WPILib BSD license file in the root directory of this project.

#include "commands/Autos.h"

#include <frc2/command/Commands.h>

#include "commands/ExampleCommand.h"

frc2::CommandPtr autos::ExampleAuto(ExampleSubsystem* subsystem) {
  return frc2::cmd::Sequence(subsystem->ExampleMethodCommand(),
                             ExampleCommand(subsystem).ToPtr());
}
```



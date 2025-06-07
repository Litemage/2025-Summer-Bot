

# File ExampleCommand.cpp

[**File List**](files.md) **>** [**commands**](dir_936b7b8edf6aa316affdf0e21f6b0c34.md) **>** [**ExampleCommand.cpp**](_example_command_8cpp.md)

[Go to the documentation of this file](_example_command_8cpp.md)


```C++
// Copyright (c) FIRST and other WPILib contributors.
// Open Source Software; you can modify and/or share it under the terms of
// the WPILib BSD license file in the root directory of this project.

#include "commands/ExampleCommand.h"

ExampleCommand::ExampleCommand(ExampleSubsystem* subsystem)
    : m_subsystem{subsystem} {
  // Register that this command requires the subsystem.
  AddRequirements(m_subsystem);
}
```





# File ExampleSubsystem.cpp

[**File List**](files.md) **>** [**cpp**](dir_fdf2b31f12d3ebb2f617242d0514024b.md) **>** [**subsystems**](dir_2a59f1b00facdb43e21fc1c516c8806d.md) **>** [**ExampleSubsystem.cpp**](_example_subsystem_8cpp.md)

[Go to the documentation of this file](_example_subsystem_8cpp.md)


```C++
// Copyright (c) FIRST and other WPILib contributors.
// Open Source Software; you can modify and/or share it under the terms of
// the WPILib BSD license file in the root directory of this project.

#include "subsystems/ExampleSubsystem.h"

ExampleSubsystem::ExampleSubsystem() {
  // Implementation of subsystem constructor goes here.
}

frc2::CommandPtr ExampleSubsystem::ExampleMethodCommand() {
  // Inline construction of command goes here.
  // Subsystem::RunOnce implicitly requires `this` subsystem.
  return RunOnce([/* this */] { /* one-time action goes here */ });
}

bool ExampleSubsystem::ExampleCondition() {
  // Query some boolean state, such as a digital sensor.
  return false;
}

void ExampleSubsystem::Periodic() {
  // Implementation of subsystem periodic method goes here.
}

void ExampleSubsystem::SimulationPeriodic() {
  // Implementation of subsystem simulation periodic method goes here.
}
```



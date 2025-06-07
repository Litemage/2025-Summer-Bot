

# File ExampleSubsystem.h

[**File List**](files.md) **>** [**include**](dir_df3bee86fdbfb464c3a94507855b0bdc.md) **>** [**subsystems**](dir_5b31952f813df36dabbaa31d5b8f92e5.md) **>** [**ExampleSubsystem.h**](_example_subsystem_8h.md)

[Go to the documentation of this file](_example_subsystem_8h.md)


```C++
// Copyright (c) FIRST and other WPILib contributors.
// Open Source Software; you can modify and/or share it under the terms of
// the WPILib BSD license file in the root directory of this project.

#pragma once

#include <frc2/command/CommandPtr.h>
#include <frc2/command/SubsystemBase.h>

class ExampleSubsystem : public frc2::SubsystemBase {
 public:
  ExampleSubsystem();

  frc2::CommandPtr ExampleMethodCommand();

  bool ExampleCondition();

  void Periodic() override;

  void SimulationPeriodic() override;

 private:
  // Components (e.g. motor controllers and sensors) should generally be
  // declared private and exposed only through public methods.
};
```



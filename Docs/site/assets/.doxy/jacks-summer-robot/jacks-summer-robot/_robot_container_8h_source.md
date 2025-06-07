

# File RobotContainer.h

[**File List**](files.md) **>** [**include**](dir_df3bee86fdbfb464c3a94507855b0bdc.md) **>** [**RobotContainer.h**](_robot_container_8h.md)

[Go to the documentation of this file](_robot_container_8h.md)


```C++
// Copyright (c) FIRST and other WPILib contributors.
// Open Source Software; you can modify and/or share it under the terms of
// the WPILib BSD license file in the root directory of this project.

#pragma once

#include <frc2/command/CommandPtr.h>
#include <frc2/command/button/CommandXboxController.h>

#include "Constants.h"
#include "subsystems/ExampleSubsystem.h"

class RobotContainer {
 public:
  RobotContainer();

  frc2::CommandPtr GetAutonomousCommand();

 private:
  // Replace with CommandPS4Controller or CommandJoystick if needed
  frc2::CommandXboxController m_driverController{
      OperatorConstants::kDriverControllerPort};

  // The robot's subsystems are defined here...
  ExampleSubsystem m_subsystem;

  void ConfigureBindings();
};
```



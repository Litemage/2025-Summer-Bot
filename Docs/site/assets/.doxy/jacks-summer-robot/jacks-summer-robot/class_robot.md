

# Class Robot



[**ClassList**](annotated.md) **>** [**Robot**](class_robot.md)








Inherits the following classes: frc::TimedRobot


































## Public Functions

| Type | Name |
| ---: | :--- |
|  void | [**AutonomousInit**](#function-autonomousinit) () override<br> |
|  void | [**AutonomousPeriodic**](#function-autonomousperiodic) () override<br> |
|  void | [**DisabledInit**](#function-disabledinit) () override<br> |
|  void | [**DisabledPeriodic**](#function-disabledperiodic) () override<br> |
|   | [**Robot**](#function-robot) () <br> |
|  void | [**RobotPeriodic**](#function-robotperiodic) () override<br> |
|  void | [**SimulationInit**](#function-simulationinit) () override<br> |
|  void | [**SimulationPeriodic**](#function-simulationperiodic) () override<br> |
|  void | [**TeleopInit**](#function-teleopinit) () override<br> |
|  void | [**TeleopPeriodic**](#function-teleopperiodic) () override<br> |
|  void | [**TestPeriodic**](#function-testperiodic) () override<br> |




























## Public Functions Documentation




### function AutonomousInit 

```C++
void Robot::AutonomousInit () override
```



This autonomous runs the autonomous command selected by your `RobotContainer` class. 


        

<hr>



### function AutonomousPeriodic 

```C++
void Robot::AutonomousPeriodic () override
```




<hr>



### function DisabledInit 

```C++
void Robot::DisabledInit () override
```



This function is called once each time the robot enters Disabled mode. You can use it to reset any subsystem information you want to clear when the robot is disabled. 


        

<hr>



### function DisabledPeriodic 

```C++
void Robot::DisabledPeriodic () override
```




<hr>



### function Robot 

```C++
Robot::Robot () 
```




<hr>



### function RobotPeriodic 

```C++
void Robot::RobotPeriodic () override
```



This function is called every 20 ms, no matter the mode. Use this for items like diagnostics that you want to run during disabled, autonomous, teleoperated and test.


This runs after the mode specific periodic functions, but before LiveWindow and SmartDashboard integrated updating. 


        

<hr>



### function SimulationInit 

```C++
void Robot::SimulationInit () override
```



This function is called once when the robot is first started up. 


        

<hr>



### function SimulationPeriodic 

```C++
void Robot::SimulationPeriodic () override
```



This function is called periodically whilst in simulation. 


        

<hr>



### function TeleopInit 

```C++
void Robot::TeleopInit () override
```




<hr>



### function TeleopPeriodic 

```C++
void Robot::TeleopPeriodic () override
```



This function is called periodically during operator control. 


        

<hr>



### function TestPeriodic 

```C++
void Robot::TestPeriodic () override
```



This function is called periodically during test mode. 


        

<hr>

------------------------------
The documentation for this class was generated from the following file `C:/Users/jsime/OneDrive/Documents/Git/2025-Summer-Bot/src/main/include/Robot.h`


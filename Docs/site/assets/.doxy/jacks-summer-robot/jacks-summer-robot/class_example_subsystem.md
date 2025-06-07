

# Class ExampleSubsystem



[**ClassList**](annotated.md) **>** [**ExampleSubsystem**](class_example_subsystem.md)








Inherits the following classes: frc2::SubsystemBase


































## Public Functions

| Type | Name |
| ---: | :--- |
|  bool | [**ExampleCondition**](#function-examplecondition) () <br> |
|  frc2::CommandPtr | [**ExampleMethodCommand**](#function-examplemethodcommand) () <br> |
|   | [**ExampleSubsystem**](#function-examplesubsystem) () <br> |
|  void | [**Periodic**](#function-periodic) () override<br> |
|  void | [**SimulationPeriodic**](#function-simulationperiodic) () override<br> |




























## Public Functions Documentation




### function ExampleCondition 

```C++
bool ExampleSubsystem::ExampleCondition () 
```



An example method querying a boolean state of the subsystem (for example, a digital sensor).




**Returns:**

value of some boolean subsystem state, such as a digital sensor. 





        

<hr>



### function ExampleMethodCommand 

```C++
frc2::CommandPtr ExampleSubsystem::ExampleMethodCommand () 
```



Example command factory method. 


        

<hr>



### function ExampleSubsystem 

```C++
ExampleSubsystem::ExampleSubsystem () 
```




<hr>



### function Periodic 

```C++
void ExampleSubsystem::Periodic () override
```



Will be called periodically whenever the CommandScheduler runs. 


        

<hr>



### function SimulationPeriodic 

```C++
void ExampleSubsystem::SimulationPeriodic () override
```



Will be called periodically whenever the CommandScheduler runs during simulation. 


        

<hr>

------------------------------
The documentation for this class was generated from the following file `C:/Users/jsime/OneDrive/Documents/Git/2025-Summer-Bot/src/main/include/subsystems/ExampleSubsystem.h`


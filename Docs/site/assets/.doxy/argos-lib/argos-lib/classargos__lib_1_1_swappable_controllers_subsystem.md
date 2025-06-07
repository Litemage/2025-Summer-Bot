

# Class argos\_lib::SwappableControllersSubsystem



[**ClassList**](annotated.md) **>** [**argos\_lib**](namespaceargos__lib.md) **>** [**SwappableControllersSubsystem**](classargos__lib_1_1_swappable_controllers_subsystem.md)



_Allows two controllers to swap between "Driver" and "Operator" control schemes on the fly by swapping the m\_driverController and m\_operatorController objects._ 

* `#include <swappable_controllers_subsystem.h>`



Inherits the following classes: frc2::SubsystemBase


































## Public Functions

| Type | Name |
| ---: | :--- |
|  [**argos\_lib::XboxController**](classargos__lib_1_1_xbox_controller.md) & | [**DriverController**](#function-drivercontroller) () <br>_Get reference to active driver controller._  |
|  [**argos\_lib::XboxController**](classargos__lib_1_1_xbox_controller.md) & | [**OperatorController**](#function-operatorcontroller) () <br>_Get reference to active operator controller._  |
|  void | [**Periodic**](#function-periodic) () override<br>_Will be called periodically whenever the CommandScheduler runs._  |
|  void | [**Swap**](#function-swap) () <br>_Swap driver and operator controller rolls._  |
|   | [**SwappableControllersSubsystem**](#function-swappablecontrollerssubsystem-12) () = delete<br> |
|   | [**SwappableControllersSubsystem**](#function-swappablecontrollerssubsystem-22) (int driverControllerPort, int operatorControllerPort) <br>_Construct a new Swappable Controllers Subsystem object with two controllers._  |
|  void | [**VibrateAll**](#function-vibrateall) (argos\_lib::VibrationModel newModel) <br>_Change vibration model for both controllers._  |




























## Public Functions Documentation




### function DriverController 

_Get reference to active driver controller._ 
```C++
argos_lib::XboxController & argos_lib::SwappableControllersSubsystem::DriverController () 
```





**Returns:**

Active driver controller based on swaps up to this point 





        

<hr>



### function OperatorController 

_Get reference to active operator controller._ 
```C++
argos_lib::XboxController & argos_lib::SwappableControllersSubsystem::OperatorController () 
```





**Returns:**

Active operator controller based on swaps up to this point 





        

<hr>



### function Periodic 

_Will be called periodically whenever the CommandScheduler runs._ 
```C++
void argos_lib::SwappableControllersSubsystem::Periodic () override
```



Will be called periodically whenever the CommandScheduler runs. 


        

<hr>



### function Swap 

_Swap driver and operator controller rolls._ 
```C++
void argos_lib::SwappableControllersSubsystem::Swap () 
```




<hr>



### function SwappableControllersSubsystem [1/2]

```C++
argos_lib::SwappableControllersSubsystem::SwappableControllersSubsystem () = delete
```




<hr>



### function SwappableControllersSubsystem [2/2]

_Construct a new Swappable Controllers Subsystem object with two controllers._ 
```C++
argos_lib::SwappableControllersSubsystem::SwappableControllersSubsystem (
    int driverControllerPort,
    int operatorControllerPort
) 
```





**Parameters:**


* `driverControllerPort` Index of driver controller 
* `operatorControllerPort` Index of operator controller 




        

<hr>



### function VibrateAll 

_Change vibration model for both controllers._ 
```C++
void argos_lib::SwappableControllersSubsystem::VibrateAll (
    argos_lib::VibrationModel newModel
) 
```




<hr>

------------------------------
The documentation for this class was generated from the following file `C:/Users/jsime/OneDrive/Documents/Git/2025-Summer-Bot/src/argos_lib/include/argos_lib/subsystems/swappable_controllers_subsystem.h`


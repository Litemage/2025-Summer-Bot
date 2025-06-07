

# Struct argos\_lib::ClosedLoopSensorConversions



[**ClassList**](annotated.md) **>** [**argos\_lib**](namespaceargos__lib.md) **>** [**ClosedLoopSensorConversions**](structargos__lib_1_1_closed_loop_sensor_conversions.md)



_Conversion factors to aid displaying sensor values as meaningful numbers._ 

* `#include <nt_motor_pid_tuner.h>`





















## Public Attributes

| Type | Name |
| ---: | :--- |
|  double | [**position**](#variable-position)   = `{1.0}`<br>_Multiply by this to convert sensor position units to physical units._  |
|  double | [**setpoint**](#variable-setpoint)   = `/* multi line expression */`<br>_Multiply by this to convert sensor setpoint units to physical units (should be the same as either position or velocity)_  |
|  double | [**velocity**](#variable-velocity)   = `{1.0}`<br>_Multiply by this to convert sensor velocity units to physical units._  |












































## Public Attributes Documentation




### variable position 

_Multiply by this to convert sensor position units to physical units._ 
```C++
double argos_lib::ClosedLoopSensorConversions::position;
```




<hr>



### variable setpoint 

_Multiply by this to convert sensor setpoint units to physical units (should be the same as either position or velocity)_ 
```C++
double argos_lib::ClosedLoopSensorConversions::setpoint;
```




<hr>



### variable velocity 

_Multiply by this to convert sensor velocity units to physical units._ 
```C++
double argos_lib::ClosedLoopSensorConversions::velocity;
```




<hr>

------------------------------
The documentation for this class was generated from the following file `C:/Users/jsime/OneDrive/Documents/Git/2025-Summer-Bot/src/argos_lib/include/argos_lib/general/nt_motor_pid_tuner.h`


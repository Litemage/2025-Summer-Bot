

# Namespace argos\_lib



[**Namespace List**](namespaces.md) **>** [**argos\_lib**](namespaceargos__lib.md)



[More...](#detailed-description)














## Namespaces

| Type | Name |
| ---: | :--- |
| namespace | [**angle**](namespaceargos__lib_1_1angle.md) <br> |
| namespace | [**cancoder\_config**](namespaceargos__lib_1_1cancoder__config.md) <br> |
| namespace | [**colors**](namespaceargos__lib_1_1colors.md) <br> |
| namespace | [**falcon\_config**](namespaceargos__lib_1_1falcon__config.md) <br> |
| namespace | [**gamma\_corrected\_colors**](namespaceargos__lib_1_1gamma__corrected__colors.md) <br> |
| namespace | [**led**](namespaceargos__lib_1_1led.md) <br> |
| namespace | [**odometry\_aim**](namespaceargos__lib_1_1odometry__aim.md) <br> |
| namespace | [**status\_frame\_config**](namespaceargos__lib_1_1status__frame__config.md) <br> |
| namespace | [**swerve**](namespaceargos__lib_1_1swerve.md) <br> |
| namespace | [**talonsrx\_config**](namespaceargos__lib_1_1talonsrx__config.md) <br> |
| namespace | [**testing**](namespaceargos__lib_1_1testing.md) <br> |
| namespace | [**triggers**](namespaceargos__lib_1_1triggers.md) <br> |


## Classes

| Type | Name |
| ---: | :--- |
| struct | [**ArgosColor**](structargos__lib_1_1_argos_color.md) <br> |
| class | [**ArgosLogger**](classargos__lib_1_1_argos_logger.md) <br>_Log to the console in a clean, repeatable manner._  |
| struct | [**CANAddress**](structargos__lib_1_1_c_a_n_address.md) <br> |
| struct | [**ClosedLoopSensorConversions**](structargos__lib_1_1_closed_loop_sensor_conversions.md) <br>_Conversion factors to aid displaying sensor values as meaningful numbers._  |
| struct | [**DebounceSettings**](structargos__lib_1_1_debounce_settings.md) <br> |
| class | [**Debouncer**](classargos__lib_1_1_debouncer.md) <br> |
| class | [**EdgeDetector**](classargos__lib_1_1_edge_detector.md) <br> |
| class | [**FSHomingStorage**](classargos__lib_1_1_f_s_homing_storage.md) &lt;class T&gt;<br>_Saves and loads home positions from filesystem._  |
| class | [**GenericDebouncer**](classargos__lib_1_1_generic_debouncer.md) &lt;class T&gt;<br> |
| class | [**HomingStorageInterface**](classargos__lib_1_1_homing_storage_interface.md) &lt;class T&gt;<br>_Interface capable of saving and loading home positions from persistent storage._  |
| class | [**HysteresisFilter**](classargos__lib_1_1_hysteresis_filter.md) &lt;typename T&gt;<br>_A simple hysteresis filter for giving a bool output for a threshold._  |
| struct | [**InterpMapPoint**](structargos__lib_1_1_interp_map_point.md) &lt;class T, class V&gt;<br>_Point that helps generate an interpolation map._  |
| class | [**InterpolationMap**](classargos__lib_1_1_interpolation_map.md) &lt;class T, size, class V&gt;<br>_Performs linear interpolation of a value based on a set of input-&gt;output mapping points._  |
| struct | [**LEDState**](structargos__lib_1_1_l_e_d_state.md) <br>_Color and animation status for an individual LED._  |
| class | [**LEDSubsystem**](classargos__lib_1_1_l_e_d_subsystem.md) <br> |
| class | [**NTMotorPIDTuner**](classargos__lib_1_1_n_t_motor_p_i_d_tuner.md) <br>_Allows user to set PID parameters from network tables and update the motor configurations on updates. Also monitors status information from motors to aid tuning._  |
| class | [**NTSubscriber**](classargos__lib_1_1_n_t_subscriber.md) <br>_Subscribes to Network Tables entry updates and calls a specified callback to use the new value._  |
| class | [**SwapControllersCommand**](classargos__lib_1_1_swap_controllers_command.md) <br>_Swaps rolls of two controllers. Useful if one controller breaks during a match._  |
| class | [**SwappableControllersSubsystem**](classargos__lib_1_1_swappable_controllers_subsystem.md) <br>_Allows two controllers to swap between "Driver" and "Operator" control schemes on the fly by swapping the m\_driverController and m\_operatorController objects._  |
| class | [**SwerveFSHomingStorage**](classargos__lib_1_1_swerve_f_s_homing_storage.md) <br> |
| class | [**SwerveHomeStorageInterface**](classargos__lib_1_1_swerve_home_storage_interface.md) <br>_Interface capable of saving and loading module home positions from persistent storage._  |
| struct | [**VibrationStatus**](structargos__lib_1_1_vibration_status.md) <br>_Vibration percentages that can be sent to controller for user feedback._  |
| class | [**XboxController**](classargos__lib_1_1_xbox_controller.md) <br> |


## Public Types

| Type | Name |
| ---: | :--- |
| enum  | [**LogLevel**](#enum-loglevel)  <br>_Represents a log level of either information, or error._  |
| enum  | [**RobotInstance**](#enum-robotinstance)  <br>_Differentiates between practice robot and competition robot._  |
| typedef std::function&lt; [**VibrationStatus**](structargos__lib_1_1_vibration_status.md)()&gt; | [**VibrationModel**](#typedef-vibrationmodel)  <br> |




## Public Attributes

| Type | Name |
| ---: | :--- |
|  std::array&lt; uint8\_t, 256 &gt; | [**gamma8**](#variable-gamma8)   = `/* multi line expression */`<br> |
















## Public Functions

| Type | Name |
| ---: | :--- |
|  [**ArgosColor**](structargos__lib_1_1_argos_color.md) | [**GammaCorrect**](#function-gammacorrect) ([**ArgosColor**](structargos__lib_1_1_argos_color.md) original) <br> |
|  double | [**GetPositionConversionFactor**](#function-getpositionconversionfactor) (Callable toPhysicalUnitsFunction) <br>_Generates a double value to convert sensor position values to physical units represented as a double._  |
|  [**RobotInstance**](namespaceargos__lib.md#enum-robotinstance) | [**GetRobotInstance**](#function-getrobotinstance) () <br>_Detect robot instance._  |
|  double | [**GetVelocityConversionFactor**](#function-getvelocityconversionfactor) (Callable toPhysicalUnitsFunction) <br>_Generates a double value to convert sensor velocity values to physical units represented as a double._  |
|  VibrationModel | [**TemporaryVibrationPattern**](#function-temporaryvibrationpattern) (VibrationModel temporaryModel, units::millisecond\_t temporaryModelDuration, VibrationModel lastingModel=[**VibrationOff**](namespaceargos__lib.md#function-vibrationoff)()) <br>_Run a vibration model for a specified duration, then run another model in perpetuity thereafter._  |
|  VibrationModel | [**VibrationAlternatePulse**](#function-vibrationalternatepulse) (units::millisecond\_t pulsePeriod, double intensityOn, double intensityOff=0.0) <br>_Toggle vibration between intensityOn and intensityOff levels. Left output is in intensityOn phase while right output is in intensityOff phase and vice-versa._  |
|  VibrationModel | [**VibrationAlternateWave**](#function-vibrationalternatewave) (units::millisecond\_t pulsePeriod, double intensityOn, double intensityOff=0.0) <br>_Smoothly transition vibration between intensityOn and intensityOff levels. Left output is in intensityOn phase while right output is in intensityOff phase and vice-versa._  |
|  VibrationModel | [**VibrationConstant**](#function-vibrationconstant) (double intensity) <br>_Set vibration to a constant value where left and right are the same intensity._  |
|  VibrationModel | [**VibrationConstant**](#function-vibrationconstant) (double intensityLeft, double intensityRight) <br>_Set vibration to a constant value where left and right have discrete intensities._  |
|  VibrationModel | [**VibrationOff**](#function-vibrationoff) () <br>_Turn off vibration._  |
|  VibrationModel | [**VibrationSyncPulse**](#function-vibrationsyncpulse) (units::millisecond\_t pulsePeriod, double intensityOn, double intensityOff=0.0) <br>_Toggle vibration between intensityOn and intensityOff levels. Left and right have the same vibration intensity._  |
|  VibrationModel | [**VibrationSyncWave**](#function-vibrationsyncwave) (units::millisecond\_t pulsePeriod, double intensityOn, double intensityOff=0.0) <br>_Smoothly transition vibration between intensityOn and intensityOff levels. Left and right have the same vibration intensity._  |
|  bool | [**operator&lt;**](#function-operator) (const [**InterpMapPoint**](structargos__lib_1_1_interp_map_point.md)&lt; T, V &gt; & a, const T & b) <br> |
|  bool | [**operator&lt;**](#function-operator_1) (const T & a, const [**InterpMapPoint**](structargos__lib_1_1_interp_map_point.md)&lt; T, V &gt; & b) <br> |


## Public Static Functions

| Type | Name |
| ---: | :--- |
|  int | [**GetCANAddr**](#function-getcanaddr) (const [**argos\_lib::CANAddress**](structargos__lib_1_1_c_a_n_address.md) & compAddress, const [**argos\_lib::CANAddress**](structargos__lib_1_1_c_a_n_address.md) & practiceAddress, [**argos\_lib::RobotInstance**](namespaceargos__lib.md#enum-robotinstance) instance) <br>_Gets integer address from_ [_**CANAddress**_](structargos__lib_1_1_c_a_n_address.md) _objects based on robot instance._ |
|  std::string\_view | [**GetCANBus**](#function-getcanbus) (const [**argos\_lib::CANAddress**](structargos__lib_1_1_c_a_n_address.md) & compAddress, const [**argos\_lib::CANAddress**](structargos__lib_1_1_c_a_n_address.md) & practiceAddress, [**argos\_lib::RobotInstance**](namespaceargos__lib.md#enum-robotinstance) instance) <br>_Gets std::string\_view bus name from_ [_**CANAddress**_](structargos__lib_1_1_c_a_n_address.md) _objects based on robot instance._ |
|  bool | [**InThreshold**](#function-inthreshold) (const T value, const T target, const T threshold) <br>_Detect if a value is within a threshold of a target value._  |


























## Detailed Description




**Copyright:**

Copyright (c) Argos FRC Team 1756. Open Source Software; you can modify and/or share it under the terms of the license file in the root directory of this project. 





    
## Public Types Documentation




### enum LogLevel 

_Represents a log level of either information, or error._ 
```C++
enum argos_lib::LogLevel {
    INFO,
    ERR
};
```




<hr>



### enum RobotInstance 

_Differentiates between practice robot and competition robot._ 
```C++
enum argos_lib::RobotInstance {
    Competition,
    Practice
};
```




<hr>



### typedef VibrationModel 

```C++
using argos_lib::VibrationModel =  std::function<VibrationStatus()>;
```




<hr>
## Public Attributes Documentation




### variable gamma8 

```C++
std::array<uint8_t, 256> argos_lib::gamma8;
```




<hr>
## Public Functions Documentation




### function GammaCorrect 

```C++
ArgosColor argos_lib::GammaCorrect (
    ArgosColor original
) 
```




<hr>



### function GetPositionConversionFactor 

_Generates a double value to convert sensor position values to physical units represented as a double._ 
```C++
template<class Callable>
double argos_lib::GetPositionConversionFactor (
    Callable toPhysicalUnitsFunction
) 
```





**Template parameters:**


* `Callable` Function that generates a units value from a double 



**Parameters:**


* `toPhysicalUnitsFunction` Conversion function 



**Returns:**

double Physical unit value stripped of unit so it's just a double 





        

<hr>



### function GetRobotInstance 

_Detect robot instance._ 
```C++
RobotInstance argos_lib::GetRobotInstance () 
```





**Returns:**

[**RobotInstance**](namespaceargos__lib.md#enum-robotinstance)




**Copyright:**

Copyright (c) Argos FRC Team 1756. Open Source Software; you can modify and/or share it under the terms of the license file in the root directory of this project. 





        

<hr>



### function GetVelocityConversionFactor 

_Generates a double value to convert sensor velocity values to physical units represented as a double._ 
```C++
template<class Callable>
double argos_lib::GetVelocityConversionFactor (
    Callable toPhysicalUnitsFunction
) 
```





**Template parameters:**


* `Callable` Function that generates a units value from a double 



**Parameters:**


* `toPhysicalUnitsFunction` Conversion function 



**Returns:**

double Physical unit value stripped of unit so it's just a double 





        

<hr>



### function TemporaryVibrationPattern 

_Run a vibration model for a specified duration, then run another model in perpetuity thereafter._ 
```C++
VibrationModel argos_lib::TemporaryVibrationPattern (
    VibrationModel temporaryModel,
    units::millisecond_t temporaryModelDuration,
    VibrationModel lastingModel=VibrationOff ()
) 
```





**Parameters:**


* `temporaryModel` Model to run for the specified duration 
* `temporaryModelDuration` Amount of time to run temporaryModel 
* `lastingModel` Model to run forever after the specified duration 



**Returns:**

VibrationModel 





        

<hr>



### function VibrationAlternatePulse 

_Toggle vibration between intensityOn and intensityOff levels. Left output is in intensityOn phase while right output is in intensityOff phase and vice-versa._ 
```C++
VibrationModel argos_lib::VibrationAlternatePulse (
    units::millisecond_t pulsePeriod,
    double intensityOn,
    double intensityOff=0.0
) 
```





**Parameters:**


* `pulsePeriod` Time to complete one intensityOn-&gt;intensityOff cycle 
* `intensityOn` Vibration percent output when in intensityOn portion of cycle [0,1.0] 
* `intensityOff` Vibration percent output when in intensityOff portion of cycle [0,1.0] 



**Returns:**

VibrationModel 





        

<hr>



### function VibrationAlternateWave 

_Smoothly transition vibration between intensityOn and intensityOff levels. Left output is in intensityOn phase while right output is in intensityOff phase and vice-versa._ 
```C++
VibrationModel argos_lib::VibrationAlternateWave (
    units::millisecond_t pulsePeriod,
    double intensityOn,
    double intensityOff=0.0
) 
```





**Parameters:**


* `pulsePeriod` Time to complete one intensityOn-&gt;intensityOff cycle 
* `intensityOn` Vibration percent output when at peak of intensityOn portion of cycle [0,1.0] 
* `intensityOff` Vibration percent output when in trough of intensityOff portion of cycle [0,1.0] 



**Returns:**

VibrationModel 





        

<hr>



### function VibrationConstant 

_Set vibration to a constant value where left and right are the same intensity._ 
```C++
VibrationModel argos_lib::VibrationConstant (
    double intensity
) 
```





**Parameters:**


* `intensity` Percent vibration output [0,1.0] 



**Returns:**

VibrationModel 





        

<hr>



### function VibrationConstant 

_Set vibration to a constant value where left and right have discrete intensities._ 
```C++
VibrationModel argos_lib::VibrationConstant (
    double intensityLeft,
    double intensityRight
) 
```





**Parameters:**


* `intensityLeft` Left vibration percent output [0,1.0] 
* `intensityRight` Right vibration percent output [0,1.0] 



**Returns:**

VibrationModel 





        

<hr>



### function VibrationOff 

_Turn off vibration._ 
```C++
VibrationModel argos_lib::VibrationOff () 
```





**Returns:**

VibrationModel 





        

<hr>



### function VibrationSyncPulse 

_Toggle vibration between intensityOn and intensityOff levels. Left and right have the same vibration intensity._ 
```C++
VibrationModel argos_lib::VibrationSyncPulse (
    units::millisecond_t pulsePeriod,
    double intensityOn,
    double intensityOff=0.0
) 
```





**Parameters:**


* `pulsePeriod` Time to complete one intensityOn-&gt;intensityOff cycle 
* `intensityOn` Vibration percent output when in intensityOn portion of cycle [0,1.0] 
* `intensityOff` Vibration percent output when in intensityOff portion of cycle [0,1.0] 



**Returns:**

VibrationModel 





        

<hr>



### function VibrationSyncWave 

_Smoothly transition vibration between intensityOn and intensityOff levels. Left and right have the same vibration intensity._ 
```C++
VibrationModel argos_lib::VibrationSyncWave (
    units::millisecond_t pulsePeriod,
    double intensityOn,
    double intensityOff=0.0
) 
```





**Parameters:**


* `pulsePeriod` Time to complete one intensityOn-&gt;intensityOff cycle 
* `intensityOn` Vibration percent output when at peak of intensityOn portion of cycle [0,1.0] 
* `intensityOff` Vibration percent output when in trough of intensityOff portion of cycle [0,1.0] 



**Returns:**

VibrationModel 





        

<hr>



### function operator&lt; 

```C++
template<class T, class V>
bool argos_lib::operator< (
    const InterpMapPoint < T, V > & a,
    const T & b
) 
```




<hr>



### function operator&lt; 

```C++
template<class T, class V>
bool argos_lib::operator< (
    const T & a,
    const InterpMapPoint < T, V > & b
) 
```




<hr>
## Public Static Functions Documentation




### function GetCANAddr 

_Gets integer address from_ [_**CANAddress**_](structargos__lib_1_1_c_a_n_address.md) _objects based on robot instance._
```C++
static inline int argos_lib::GetCANAddr (
    const argos_lib::CANAddress & compAddress,
    const argos_lib::CANAddress & practiceAddress,
    argos_lib::RobotInstance instance
) 
```





**Parameters:**


* `compAddress` The competiton robot [**CANAddress**](structargos__lib_1_1_c_a_n_address.md) object 
* `practiceAddress` The practice robot [**CANAddress**](structargos__lib_1_1_c_a_n_address.md) object 
* `instance` Current instance of robot 



**Returns:**

returns compAddress.addr if instance is competition, practiceAddress.addr if instance is practice 





        

<hr>



### function GetCANBus 

_Gets std::string\_view bus name from_ [_**CANAddress**_](structargos__lib_1_1_c_a_n_address.md) _objects based on robot instance._
```C++
static inline std::string_view argos_lib::GetCANBus (
    const argos_lib::CANAddress & compAddress,
    const argos_lib::CANAddress & practiceAddress,
    argos_lib::RobotInstance instance
) 
```





**Parameters:**


* `compAddress` The competiton robot [**CANAddress**](structargos__lib_1_1_c_a_n_address.md) object 
* `practiceAddress` The practice robot [**CANAddress**](structargos__lib_1_1_c_a_n_address.md) object 
* `instance` Current instance of robot 



**Returns:**

returns compAddress.busName if instance is competition, practiceAddress.busName if instance is practice 





        

<hr>



### function InThreshold 

_Detect if a value is within a threshold of a target value._ 
```C++
template<typename T>
static bool argos_lib::InThreshold (
    const T value,
    const T target,
    const T threshold
) 
```





**Template parameters:**


* `T` Type that implements operator+(), operator-(), operator&lt;=() and operator&gt;=() 



**Parameters:**


* `value` Value to check 
* `target` Center of range 
* `threshold` Allowable error from target 



**Returns:**

true when value is within threshold of target, false otherwise 





        

<hr>

------------------------------
The documentation for this class was generated from the following file `C:/Users/jsime/OneDrive/Documents/Git/2025-Summer-Bot/src/argos_lib/include/argos_lib/commands/swap_controllers_command.h`


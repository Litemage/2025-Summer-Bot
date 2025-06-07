

# Namespace argos\_lib::status\_frame\_config



[**Namespace List**](namespaces.md) **>** [**argos\_lib**](namespaceargos__lib.md) **>** [**status\_frame\_config**](namespaceargos__lib_1_1status__frame__config.md)






















## Public Types

| Type | Name |
| ---: | :--- |
| typedef ctre::phoenix6::hardware::core::CoreTalonFX | [**BaseTalon**](#typedef-basetalon)  <br> |
| enum  | [**MotorPresetMode**](#enum-motorpresetmode)  <br>_Motor mode used for setting status frame update periods._  |




















## Public Functions

| Type | Name |
| ---: | :--- |
|  void | [**SetMotorStatusFrameRates**](#function-setmotorstatusframerates) (BaseTalon & motor, MotorPresetMode motorMode) <br>_Set motor controller status frame update periods based on the motor preset._  |




























## Public Types Documentation




### typedef BaseTalon 

```C++
using argos_lib::status_frame_config::BaseTalon =  ctre::phoenix6::hardware::core::CoreTalonFX;
```




<hr>



### enum MotorPresetMode 

_Motor mode used for setting status frame update periods._ 
```C++
enum argos_lib::status_frame_config::MotorPresetMode {
    Basic,
    BasicFX,
    Leader,
    LeaderFX,
    Follower,
    FollowerFX,
    MotionProfiling,
    MotionProfilingFX,
    Tuning,
    TuningFX
};
```




<hr>
## Public Functions Documentation




### function SetMotorStatusFrameRates 

_Set motor controller status frame update periods based on the motor preset._ 
```C++
void argos_lib::status_frame_config::SetMotorStatusFrameRates (
    BaseTalon & motor,
    MotorPresetMode motorMode
) 
```





**Parameters:**


* `motor` Motor controller to configure 
* `motorMode` Preset mode to use 




        

<hr>

------------------------------
The documentation for this class was generated from the following file `C:/Users/jsime/OneDrive/Documents/Git/2025-Summer-Bot/src/argos_lib/include/argos_lib/config/status_frame_config.h`


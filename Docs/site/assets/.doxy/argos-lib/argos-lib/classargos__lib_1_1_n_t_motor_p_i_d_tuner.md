

# Class argos\_lib::NTMotorPIDTuner



[**ClassList**](annotated.md) **>** [**argos\_lib**](namespaceargos__lib.md) **>** [**NTMotorPIDTuner**](classargos__lib_1_1_n_t_motor_p_i_d_tuner.md)



_Allows user to set PID parameters from network tables and update the motor configurations on updates. Also monitors status information from motors to aid tuning._ [More...](#detailed-description)

* `#include <nt_motor_pid_tuner.h>`





































## Public Functions

| Type | Name |
| ---: | :--- |
|   | [**NTMotorPIDTuner**](#function-ntmotorpidtuner) (const std::string & tableName, std::initializer\_list&lt; BaseTalon \* &gt; motors, unsigned pidSlot, [**ClosedLoopSensorConversions**](structargos__lib_1_1_closed_loop_sensor_conversions.md) sensorConversions={}) <br>_Construct a new_ [_**NTMotorPIDTuner**_](classargos__lib_1_1_n_t_motor_p_i_d_tuner.md) _object._ |
|   | [**~NTMotorPIDTuner**](#function-ntmotorpidtuner) () <br>_Destroy the_ [_**NTMotorPIDTuner**_](classargos__lib_1_1_n_t_motor_p_i_d_tuner.md) _object._ |




























## Detailed Description




**Note:**

This runs a background thread to read statuses of motors without calling repeatedly 





    
## Public Functions Documentation




### function NTMotorPIDTuner 

_Construct a new_ [_**NTMotorPIDTuner**_](classargos__lib_1_1_n_t_motor_p_i_d_tuner.md) _object._
```C++
argos_lib::NTMotorPIDTuner::NTMotorPIDTuner (
    const std::string & tableName,
    std::initializer_list< BaseTalon * > motors,
    unsigned pidSlot,
    ClosedLoopSensorConversions sensorConversions={}
) 
```





**Parameters:**


* `tableName` Root table in which to make tuning and status keys 
* `motors` Pointers to motors that should be monitored and configured. Can be one motor if only one motor uses the control loop parameters 
* `pidSlot` PID slot to save tunes into 
* `sensorConversions` Sensor conversion factors to make status values human readable 




        

<hr>



### function ~NTMotorPIDTuner 

_Destroy the_ [_**NTMotorPIDTuner**_](classargos__lib_1_1_n_t_motor_p_i_d_tuner.md) _object._
```C++
argos_lib::NTMotorPIDTuner::~NTMotorPIDTuner () 
```




<hr>

------------------------------
The documentation for this class was generated from the following file `C:/Users/jsime/OneDrive/Documents/Git/2025-Summer-Bot/src/argos_lib/include/argos_lib/general/nt_motor_pid_tuner.h`


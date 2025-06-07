

# Namespace argos\_lib::falcon\_config



[**Namespace List**](namespaces.md) **>** [**argos\_lib**](namespaceargos__lib.md) **>** [**falcon\_config**](namespaceargos__lib_1_1falcon__config.md)










































## Public Functions

| Type | Name |
| ---: | :--- |
|  bool | [**FalconConfig**](#function-falconconfig) (ctre::phoenix6::hardware::TalonFX & motorController, units::millisecond\_t configTimeout) <br>_Configures a CTRE Falcon with only the fields provided. All other fields are given the factory default values._  |
|  bool | [**FalconConfig**](#function-falconconfig) (ctre::phoenix6::hardware::TalonFX & motorController, units::millisecond\_t configTimeout, [**argos\_lib::RobotInstance**](namespaceargos__lib.md#enum-robotinstance) instance) <br>_Configures a CTRE Falcon with configuration values according to specified robot instance._  |




























## Public Functions Documentation




### function FalconConfig 

_Configures a CTRE Falcon with only the fields provided. All other fields are given the factory default values._ 
```C++
template<typename T>
bool argos_lib::falcon_config::FalconConfig (
    ctre::phoenix6::hardware::TalonFX & motorController,
    units::millisecond_t configTimeout
) 
```





**Template parameters:**


* `T` Structure containing any combination of the following members:
  * forwardLimit\_deviceID
  * forwardLimit\_normalState
  * forwardLimit\_source
  * inverted
  * neutralDeadband
  * neutralMode
  * dutyCycleNeutralDeadband
  * peakOutputForward
  * peakOutputReverse
  * voltageOpenLoopRampPeriod
  * dutyCycleOpenLoopRampPeriod
  * pid0\_kP
  * pid0\_kI
  * pid0\_kD
  * pid0\_kS
  * pid0\_kV
  * pid0\_kA
  * pid0\_kG
  * pid0\_gravityType
  * pid1\_kP
  * pid1\_kI
  * pid1\_kD
  * pid1\_kS
  * pid1\_kV
  * pid1\_kA
  * pid1\_kG
  * pid1\_gravityType
  * motionMagic\_cruiseVelocity
  * motionMagic\_acceleration
  * motionMagic\_jerk
  * motionMagic\_expo\_kV
  * motionMagic\_expo\_kA
  * reverseLimit\_deviceID
  * reverseLimit\_normalState
  * reverseLimit\_source
  * rotorToSensorRatio
  * selectedSensor
  * selectedSensor\_addr
  * sensorToMechanismRatio
  * statorCurrentLimit
  * statusFrameMotorMode
  * supplyCurrentLimit
  * supplyCurrentLowerLimit
  * supplyCurrentLowerTime 





**Parameters:**


* `motorController` Falcon object to configure 
* `configTimeout` Time to wait for response from Falcon 



**Returns:**

true Configuration succeeded 




**Returns:**

false Configuration failed 





        

<hr>



### function FalconConfig 

_Configures a CTRE Falcon with configuration values according to specified robot instance._ 
```C++
template<typename CompetitionConfig, typename PracticeConfig>
bool argos_lib::falcon_config::FalconConfig (
    ctre::phoenix6::hardware::TalonFX & motorController,
    units::millisecond_t configTimeout,
    argos_lib::RobotInstance instance
) 
```





**Template parameters:**


* `CompetitionConfig` Configurations to use in competition robot instance 
* `PracticeConfig` Configurations to use in practice robot instance 



**Parameters:**


* `motorController` Falcon object to configure 
* `configTimeout` Time to wait for response from Falcon 
* `instance` Robot instance to use 



**Returns:**

true Configuration succeeded 




**Returns:**

false Configuration failed 





        

<hr>

------------------------------
The documentation for this class was generated from the following file `C:/Users/jsime/OneDrive/Documents/Git/2025-Summer-Bot/src/argos_lib/include/argos_lib/config/falcon_config.h`


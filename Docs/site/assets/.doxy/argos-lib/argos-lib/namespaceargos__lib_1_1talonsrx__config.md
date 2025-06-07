

# Namespace argos\_lib::talonsrx\_config



[**Namespace List**](namespaces.md) **>** [**argos\_lib**](namespaceargos__lib.md) **>** [**talonsrx\_config**](namespaceargos__lib_1_1talonsrx__config.md)










































## Public Functions

| Type | Name |
| ---: | :--- |
|  bool | [**TalonSRXConfig**](#function-talonsrxconfig) (ctre::phoenix::motorcontrol::can::TalonSRX & motorController, units::millisecond\_t configTimeout) <br>_Configures a CTRE TalonSRX with only the fields provided. All other fields are given the factory default values._  |
|  bool | [**TalonSRXConfig**](#function-talonsrxconfig) (ctre::phoenix::motorcontrol::can::TalonSRX & motorController, units::millisecond\_t configTimeout, [**argos\_lib::RobotInstance**](namespaceargos__lib.md#enum-robotinstance) instance) <br>_Configures a CTRE TalonSRX with configuration values according to specified robot instance._  |




























## Public Functions Documentation




### function TalonSRXConfig 

_Configures a CTRE TalonSRX with only the fields provided. All other fields are given the factory default values._ 
```C++
template<typename T>
bool argos_lib::talonsrx_config::TalonSRXConfig (
    ctre::phoenix::motorcontrol::can::TalonSRX & motorController,
    units::millisecond_t configTimeout
) 
```





**Template parameters:**


* `T` Structure containing any combination of the following members:
  * inverted
  * neutralMode
  * pid0\_allowableError
  * pid0\_iZone
  * pid0\_kD,
  * pid0\_kF
  * pid0\_kI
  * pid0\_kP
  * pid0\_selectedSensor
  * remoteFilter0\_addr,
  * remoteFilter0\_type
  * sensorPhase
  * voltCompSat
  * statusFrameMotorMode
  * peakCurrentLimit
  * peakCurrentDuration
  * continuousCurrentLimit
  * peakOutputForward
  * peakOutputReverse
  * forwardLimitSwitchSource
  * reverseLimitSwitchSource
  * forwardLimitSwitchNormal
  * reverseLimitSwitchNormal 





**Parameters:**


* `motorController` TalonSRX object to configure 
* `configTimeout` Time to wait for response from TalonSRX 



**Returns:**

true Configuration succeeded 




**Returns:**

false Configuration failed 





        

<hr>



### function TalonSRXConfig 

_Configures a CTRE TalonSRX with configuration values according to specified robot instance._ 
```C++
template<typename CompetitionConfig, typename PracticeConfig>
bool argos_lib::talonsrx_config::TalonSRXConfig (
    ctre::phoenix::motorcontrol::can::TalonSRX & motorController,
    units::millisecond_t configTimeout,
    argos_lib::RobotInstance instance
) 
```





**Template parameters:**


* `CompetitionConfig` Configurations to use in competition robot instance 
* `PracticeConfig` Configurations to use in practice robot instance 



**Parameters:**


* `motorController` TalonSRX object to configure 
* `configTimeout` Time to wait for response from TalonSRX 
* `instance` Robot instance to use 



**Returns:**

true Configuration succeeded 




**Returns:**

false Configuration failed 





        

<hr>

------------------------------
The documentation for this class was generated from the following file `C:/Users/jsime/OneDrive/Documents/Git/2025-Summer-Bot/src/argos_lib/include/argos_lib/config/talonsrx_config.h`


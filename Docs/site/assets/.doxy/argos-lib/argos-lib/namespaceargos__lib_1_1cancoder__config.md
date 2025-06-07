

# Namespace argos\_lib::cancoder\_config



[**Namespace List**](namespaces.md) **>** [**argos\_lib**](namespaceargos__lib.md) **>** [**cancoder\_config**](namespaceargos__lib_1_1cancoder__config.md)






















## Public Types

| Type | Name |
| ---: | :--- |
| typedef ctre::phoenix6::hardware::CANcoder | [**CANcoder**](#typedef-cancoder)  <br> |




















## Public Functions

| Type | Name |
| ---: | :--- |
|  bool | [**CanCoderConfig**](#function-cancoderconfig) (CANcoder & encoder, units::millisecond\_t configTimeout) <br>_Configures a CTRE CanCoder with only the fields provided. All other fields are given the factory default values._  |
|  bool | [**CanCoderConfig**](#function-cancoderconfig) (CANcoder & encoder, units::millisecond\_t configTimeout, [**argos\_lib::RobotInstance**](namespaceargos__lib.md#enum-robotinstance) instance) <br>_Configures a CTRE CanCoder with configuration values according to specified robot instance._  |




























## Public Types Documentation




### typedef CANcoder 

```C++
using argos_lib::cancoder_config::CANcoder =  ctre::phoenix6::hardware::CANcoder;
```




<hr>
## Public Functions Documentation




### function CanCoderConfig 

_Configures a CTRE CanCoder with only the fields provided. All other fields are given the factory default values._ 
```C++
template<typename T>
bool argos_lib::cancoder_config::CanCoderConfig (
    CANcoder & encoder,
    units::millisecond_t configTimeout
) 
```





**Template parameters:**


* `T` Structure containing any combination of the following members:
  * direction
  * magOffset
  * absoluteSensorDiscontinuityPoint 





**Parameters:**


* `encoder` CANcoder object to configure 
* `configTimeout` Time to wait for response from CANcoder 



**Returns:**

true Configuration succeeded 




**Returns:**

false Configuration failed 





        

<hr>



### function CanCoderConfig 

_Configures a CTRE CanCoder with configuration values according to specified robot instance._ 
```C++
template<typename CompetitionConfig, typename PracticeConfig>
bool argos_lib::cancoder_config::CanCoderConfig (
    CANcoder & encoder,
    units::millisecond_t configTimeout,
    argos_lib::RobotInstance instance
) 
```





**Template parameters:**


* `CompetitionConfig` Configurations to use in competition robot instance 
* `PracticeConfig` Configurations to use in practice robot instance 



**Parameters:**


* `encoder` CANcoder object to configure 
* `configTimeout` Time to wait for response from CANcoder 
* `instance` Robot instance to use 



**Returns:**

true Configuration succeeded 




**Returns:**

false Configuration failed 





        

<hr>

------------------------------
The documentation for this class was generated from the following file `C:/Users/jsime/OneDrive/Documents/Git/2025-Summer-Bot/src/argos_lib/include/argos_lib/config/cancoder_config.h`


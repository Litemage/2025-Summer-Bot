

# Namespace argos\_lib::swerve



[**Namespace List**](namespaces.md) **>** [**argos\_lib**](namespaceargos__lib.md) **>** [**swerve**](namespaceargos__lib_1_1swerve.md)




















## Classes

| Type | Name |
| ---: | :--- |
| class | [**NetworkTablesHomingStorage**](classargos__lib_1_1swerve_1_1_network_tables_homing_storage.md) <br>_Saves and loads swerve module homes to networkTables._  |
| struct | [**SwerveModulePositions**](structargos__lib_1_1swerve_1_1_swerve_module_positions.md) <br>_Representation of the absolute encoder position of each module at home position._  |
| struct | [**TranslationSpeeds**](structargos__lib_1_1swerve_1_1_translation_speeds.md) <br>_Translation speeds as percent max output._  |






















## Public Functions

| Type | Name |
| ---: | :--- |
|  [**TranslationSpeeds**](structargos__lib_1_1swerve_1_1_translation_speeds.md) | [**CircularInterpolate**](#function-circularinterpolate) (const [**TranslationSpeeds**](structargos__lib_1_1swerve_1_1_translation_speeds.md) rawSpeeds, const T interpMap) <br>_Use_ [_**argos\_lib::InterpolationMap**_](classargos__lib_1_1_interpolation_map.md) _to apply mapping according to joystick vector magnitude._ |
|  frc::SwerveModuleState | [**Optimize**](#function-optimize) (frc::SwerveModuleState desiredState, units::degree\_t currentModuleAngle, units::degrees\_per\_second\_t currentModuleAngularRate, units::feet\_per\_second\_t currentModuleDriveVel, units::feet\_per\_second\_t maxVelocity) <br>_Optimize swerve module to minimize rotations and drive direction changes._  |




























## Public Functions Documentation




### function CircularInterpolate 

_Use_ [_**argos\_lib::InterpolationMap**_](classargos__lib_1_1_interpolation_map.md) _to apply mapping according to joystick vector magnitude._
```C++
template<class T>
TranslationSpeeds argos_lib::swerve::CircularInterpolate (
    const TranslationSpeeds rawSpeeds,
    const T interpMap
) 
```





**Template parameters:**


* `T` Type of interpolated input 



**Parameters:**


* `rawSpeeds` Joystick inputs as percentages 
* `interpMap` Interpolation map to apply to magnitudes 



**Returns:**

Remapped joystick percentages. Angle of vector will match rawSpeeds, but magnitude will scale according to interpMap. This results in circular deadband and other mapping results. 





        

<hr>



### function Optimize 

_Optimize swerve module to minimize rotations and drive direction changes._ 
```C++
frc::SwerveModuleState argos_lib::swerve::Optimize (
    frc::SwerveModuleState desiredState,
    units::degree_t currentModuleAngle,
    units::degrees_per_second_t currentModuleAngularRate,
    units::feet_per_second_t currentModuleDriveVel,
    units::feet_per_second_t maxVelocity
) 
```





**Parameters:**


* `desiredState` Requested state. Output must result in same motion 
* `currentModuleAngle` Module rotation angle in relative or absolute position 
* `currentModuleAngularRate` Current module rotation speed. To prevent rapid changes in rotation direction. 
* `currentModuleDriveVel` Current module drive velocity. To prevent rapid changes in drive motor velocity. 
* `maxVelocity` Max velocity for determining max transition change thresholds 



**Returns:**

Optimized swerve module state that results in same motion as desiredState 





        

<hr>

------------------------------
The documentation for this class was generated from the following file `C:/Users/jsime/OneDrive/Documents/Git/2025-Summer-Bot/src/argos_lib/include/argos_lib/general/swerve_utils.h`


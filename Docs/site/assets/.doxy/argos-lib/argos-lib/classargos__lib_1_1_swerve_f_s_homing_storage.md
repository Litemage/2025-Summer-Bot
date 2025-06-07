

# Class argos\_lib::SwerveFSHomingStorage



[**ClassList**](annotated.md) **>** [**argos\_lib**](namespaceargos__lib.md) **>** [**SwerveFSHomingStorage**](classargos__lib_1_1_swerve_f_s_homing_storage.md)








Inherits the following classes: [argos\_lib::SwerveHomeStorageInterface](classargos__lib_1_1_swerve_home_storage_interface.md)






















































## Public Functions

| Type | Name |
| ---: | :--- |
| virtual std::optional&lt; [**argos\_lib::swerve::SwerveModulePositions**](structargos__lib_1_1swerve_1_1_swerve_module_positions.md) &gt; | [**Load**](#function-load) () override<br>_Load absolute positions that represent 0 degree module orientations._  |
| virtual bool | [**Save**](#function-save) (const [**argos\_lib::swerve::SwerveModulePositions**](structargos__lib_1_1swerve_1_1_swerve_module_positions.md) & homePosition) override<br>_Save positions as new homes._  |
|   | [**SwerveFSHomingStorage**](#function-swervefshomingstorage) (const fs::path & swerveHomesPath) <br>_Construct a new File System Homing Storage object._  |


## Public Functions inherited from argos_lib::SwerveHomeStorageInterface

See [argos\_lib::SwerveHomeStorageInterface](classargos__lib_1_1_swerve_home_storage_interface.md)

| Type | Name |
| ---: | :--- |
| virtual std::optional&lt; [**argos\_lib::swerve::SwerveModulePositions**](structargos__lib_1_1swerve_1_1_swerve_module_positions.md) &gt; | [**Load**](classargos__lib_1_1_swerve_home_storage_interface.md#function-load) () = 0<br>_Load home position from persistent storage._  |
| virtual bool | [**Save**](classargos__lib_1_1_swerve_home_storage_interface.md#function-save) (const [**argos\_lib::swerve::SwerveModulePositions**](structargos__lib_1_1swerve_1_1_swerve_module_positions.md) & homePosition) = 0<br>_Save home position to persistent storage._  |






















































## Public Functions Documentation




### function Load 

_Load absolute positions that represent 0 degree module orientations._ 
```C++
virtual std::optional< argos_lib::swerve::SwerveModulePositions > argos_lib::SwerveFSHomingStorage::Load () override
```





**Returns:**

Saved module positions if they exist, otherwise std::nullopt to indicate failure 





        
Implements [*argos\_lib::SwerveHomeStorageInterface::Load*](classargos__lib_1_1_swerve_home_storage_interface.md#function-load)


<hr>



### function Save 

_Save positions as new homes._ 
```C++
virtual bool argos_lib::SwerveFSHomingStorage::Save (
    const argos_lib::swerve::SwerveModulePositions & homePosition
) override
```





**Parameters:**


* `homePosition` Positions that represent 0 degree module orientations 



**Returns:**

true if save successful, false otherwise 





        
Implements [*argos\_lib::SwerveHomeStorageInterface::Save*](classargos__lib_1_1_swerve_home_storage_interface.md#function-save)


<hr>



### function SwerveFSHomingStorage 

_Construct a new File System Homing Storage object._ 
```C++
explicit argos_lib::SwerveFSHomingStorage::SwerveFSHomingStorage (
    const fs::path & swerveHomesPath
) 
```





**Parameters:**


* `swerveHomesPath` File path relative to home directory to save into and load from 




        

<hr>

------------------------------
The documentation for this class was generated from the following file `C:/Users/jsime/OneDrive/Documents/Git/2025-Summer-Bot/src/argos_lib/include/argos_lib/homing/fs_homing.h`


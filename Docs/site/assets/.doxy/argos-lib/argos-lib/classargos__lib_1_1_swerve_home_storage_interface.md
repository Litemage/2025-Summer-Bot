

# Class argos\_lib::SwerveHomeStorageInterface



[**ClassList**](annotated.md) **>** [**argos\_lib**](namespaceargos__lib.md) **>** [**SwerveHomeStorageInterface**](classargos__lib_1_1_swerve_home_storage_interface.md)



_Interface capable of saving and loading module home positions from persistent storage._ 

* `#include <homing_interface.h>`





Inherited by the following classes: [argos\_lib::SwerveFSHomingStorage](classargos__lib_1_1_swerve_f_s_homing_storage.md),  [argos\_lib::swerve::NetworkTablesHomingStorage](classargos__lib_1_1swerve_1_1_network_tables_homing_storage.md)
































## Public Functions

| Type | Name |
| ---: | :--- |
| virtual std::optional&lt; [**argos\_lib::swerve::SwerveModulePositions**](structargos__lib_1_1swerve_1_1_swerve_module_positions.md) &gt; | [**Load**](#function-load) () = 0<br>_Load home position from persistent storage._  |
| virtual bool | [**Save**](#function-save) (const [**argos\_lib::swerve::SwerveModulePositions**](structargos__lib_1_1swerve_1_1_swerve_module_positions.md) & homePosition) = 0<br>_Save home position to persistent storage._  |




























## Public Functions Documentation




### function Load 

_Load home position from persistent storage._ 
```C++
virtual std::optional< argos_lib::swerve::SwerveModulePositions > argos_lib::SwerveHomeStorageInterface::Load () = 0
```





**Returns:**

Poisitions from persistent storage or std::nullopt if load failed or no positions were previously stored 





        

<hr>



### function Save 

_Save home position to persistent storage._ 
```C++
virtual bool argos_lib::SwerveHomeStorageInterface::Save (
    const argos_lib::swerve::SwerveModulePositions & homePosition
) = 0
```





**Parameters:**


* `homePosition` Positions to store 



**Returns:**

true Save successful 




**Returns:**

false Error saving 





        

<hr>

------------------------------
The documentation for this class was generated from the following file `C:/Users/jsime/OneDrive/Documents/Git/2025-Summer-Bot/src/argos_lib/include/argos_lib/homing/homing_interface.h`


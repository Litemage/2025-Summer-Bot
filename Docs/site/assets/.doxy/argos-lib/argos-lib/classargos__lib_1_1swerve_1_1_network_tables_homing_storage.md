

# Class argos\_lib::swerve::NetworkTablesHomingStorage



[**ClassList**](annotated.md) **>** [**argos\_lib**](namespaceargos__lib.md) **>** [**swerve**](namespaceargos__lib_1_1swerve.md) **>** [**NetworkTablesHomingStorage**](classargos__lib_1_1swerve_1_1_network_tables_homing_storage.md)



_Saves and loads swerve module homes to networkTables._ 

* `#include <network_tables_homing_storage.h>`



Inherits the following classes: [argos\_lib::SwerveHomeStorageInterface](classargos__lib_1_1_swerve_home_storage_interface.md)






















































## Public Functions

| Type | Name |
| ---: | :--- |
| virtual std::optional&lt; [**argos\_lib::swerve::SwerveModulePositions**](structargos__lib_1_1swerve_1_1_swerve_module_positions.md) &gt; | [**Load**](#function-load) () override<br>_Load home positions from network tables._  |
|   | [**NetworkTablesHomingStorage**](#function-networktableshomingstorage) (const std::string & tableName, const std::string & frontLeftPath, const std::string & frontRightPath, const std::string & rearRightPath, const std::string & rearLeftPath) <br>_Construct a new Network Tables Homing Storage object._  |
| virtual bool | [**Save**](#function-save) (const [**argos\_lib::swerve::SwerveModulePositions**](structargos__lib_1_1swerve_1_1_swerve_module_positions.md) & homePosition) override<br>_Save home positions to network tables._  |


## Public Functions inherited from argos_lib::SwerveHomeStorageInterface

See [argos\_lib::SwerveHomeStorageInterface](classargos__lib_1_1_swerve_home_storage_interface.md)

| Type | Name |
| ---: | :--- |
| virtual std::optional&lt; [**argos\_lib::swerve::SwerveModulePositions**](structargos__lib_1_1swerve_1_1_swerve_module_positions.md) &gt; | [**Load**](classargos__lib_1_1_swerve_home_storage_interface.md#function-load) () = 0<br>_Load home position from persistent storage._  |
| virtual bool | [**Save**](classargos__lib_1_1_swerve_home_storage_interface.md#function-save) (const [**argos\_lib::swerve::SwerveModulePositions**](structargos__lib_1_1swerve_1_1_swerve_module_positions.md) & homePosition) = 0<br>_Save home position to persistent storage._  |






















































## Public Functions Documentation




### function Load 

_Load home positions from network tables._ 
```C++
virtual std::optional< argos_lib::swerve::SwerveModulePositions > argos_lib::swerve::NetworkTablesHomingStorage::Load () override
```





**Returns:**

Loaded positions or nullopt if failed 





        
Implements [*argos\_lib::SwerveHomeStorageInterface::Load*](classargos__lib_1_1_swerve_home_storage_interface.md#function-load)


<hr>



### function NetworkTablesHomingStorage 

_Construct a new Network Tables Homing Storage object._ 
```C++
argos_lib::swerve::NetworkTablesHomingStorage::NetworkTablesHomingStorage (
    const std::string & tableName,
    const std::string & frontLeftPath,
    const std::string & frontRightPath,
    const std::string & rearRightPath,
    const std::string & rearLeftPath
) 
```





**Parameters:**


* `tableName` Network table name 
* `frontLeftPath` Key name for front left module 
* `frontRightPath` Key name for front right module 
* `rearRightPath` Key name for rear right module 
* `rearLeftPath` Key name for rear left module 




        

<hr>



### function Save 

_Save home positions to network tables._ 
```C++
virtual bool argos_lib::swerve::NetworkTablesHomingStorage::Save (
    const argos_lib::swerve::SwerveModulePositions & homePosition
) override
```





**Parameters:**


* `homePosition` Positions to store 



**Returns:**

true if successful 





        
Implements [*argos\_lib::SwerveHomeStorageInterface::Save*](classargos__lib_1_1_swerve_home_storage_interface.md#function-save)


<hr>

------------------------------
The documentation for this class was generated from the following file `C:/Users/jsime/OneDrive/Documents/Git/2025-Summer-Bot/src/argos_lib/include/argos_lib/homing/network_tables_homing_storage.h`


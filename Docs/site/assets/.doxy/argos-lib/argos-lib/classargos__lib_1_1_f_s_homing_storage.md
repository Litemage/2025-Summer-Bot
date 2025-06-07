

# Class argos\_lib::FSHomingStorage

**template &lt;class T&gt;**



[**ClassList**](annotated.md) **>** [**argos\_lib**](namespaceargos__lib.md) **>** [**FSHomingStorage**](classargos__lib_1_1_f_s_homing_storage.md)



_Saves and loads home positions from filesystem._ [More...](#detailed-description)

* `#include <fs_homing.h>`



Inherits the following classes: [argos\_lib::HomingStorageInterface](classargos__lib_1_1_homing_storage_interface.md)






















































## Public Functions

| Type | Name |
| ---: | :--- |
|   | [**FSHomingStorage**](#function-fshomingstorage) (const fs::path & homeFilePath) <br>_Construct a new_ [_**FSHomingStorage**_](classargos__lib_1_1_f_s_homing_storage.md) _object._ |
| virtual std::optional&lt; T &gt; | [**Load**](#function-load) () override<br>_Load home position from persistent storage._  |
| virtual bool | [**Save**](#function-save) (const T & homePosition) override<br>_Save home position to persistent storage._  |


## Public Functions inherited from argos_lib::HomingStorageInterface

See [argos\_lib::HomingStorageInterface](classargos__lib_1_1_homing_storage_interface.md)

| Type | Name |
| ---: | :--- |
| virtual std::optional&lt; T &gt; | [**Load**](classargos__lib_1_1_homing_storage_interface.md#function-load) () = 0<br>_Load home position from persistent storage._  |
| virtual bool | [**Save**](classargos__lib_1_1_homing_storage_interface.md#function-save) (const T & homePosition) = 0<br>_Save home position to persistent storage._  |






















































## Detailed Description




**Template parameters:**


* `T` Type of the home position. Should be a units type 




    
## Public Functions Documentation




### function FSHomingStorage 

_Construct a new_ [_**FSHomingStorage**_](classargos__lib_1_1_f_s_homing_storage.md) _object._
```C++
inline explicit argos_lib::FSHomingStorage::FSHomingStorage (
    const fs::path & homeFilePath
) 
```





**Parameters:**


* `homeFilePath` Path to save homes to relative to internally-managed root directory 




        

<hr>



### function Load 

_Load home position from persistent storage._ 
```C++
inline virtual std::optional< T > argos_lib::FSHomingStorage::Load () override
```





**Returns:**

Poisition from persistent storage or std::nullopt if load failed or no positions were previously stored 





        
Implements [*argos\_lib::HomingStorageInterface::Load*](classargos__lib_1_1_homing_storage_interface.md#function-load)


<hr>



### function Save 

_Save home position to persistent storage._ 
```C++
inline virtual bool argos_lib::FSHomingStorage::Save (
    const T & homePosition
) override
```





**Parameters:**


* `homePosition` Position to store 



**Returns:**

true Save successful 




**Returns:**

false Error saving 





        
Implements [*argos\_lib::HomingStorageInterface::Save*](classargos__lib_1_1_homing_storage_interface.md#function-save)


<hr>

------------------------------
The documentation for this class was generated from the following file `C:/Users/jsime/OneDrive/Documents/Git/2025-Summer-Bot/src/argos_lib/include/argos_lib/homing/fs_homing.h`


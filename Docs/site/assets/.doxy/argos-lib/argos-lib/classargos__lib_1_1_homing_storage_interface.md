

# Class argos\_lib::HomingStorageInterface

**template &lt;class T&gt;**



[**ClassList**](annotated.md) **>** [**argos\_lib**](namespaceargos__lib.md) **>** [**HomingStorageInterface**](classargos__lib_1_1_homing_storage_interface.md)



_Interface capable of saving and loading home positions from persistent storage._ [More...](#detailed-description)

* `#include <homing_interface.h>`





Inherited by the following classes: [argos\_lib::FSHomingStorage](classargos__lib_1_1_f_s_homing_storage.md)
































## Public Functions

| Type | Name |
| ---: | :--- |
| virtual std::optional&lt; T &gt; | [**Load**](#function-load) () = 0<br>_Load home position from persistent storage._  |
| virtual bool | [**Save**](#function-save) (const T & homePosition) = 0<br>_Save home position to persistent storage._  |




























## Detailed Description




**Template parameters:**


* `T` Type of the home position. Should be a units type 




    
## Public Functions Documentation




### function Load 

_Load home position from persistent storage._ 
```C++
virtual std::optional< T > argos_lib::HomingStorageInterface::Load () = 0
```





**Returns:**

Poisition from persistent storage or std::nullopt if load failed or no positions were previously stored 





        

<hr>



### function Save 

_Save home position to persistent storage._ 
```C++
virtual bool argos_lib::HomingStorageInterface::Save (
    const T & homePosition
) = 0
```





**Parameters:**


* `homePosition` Position to store 



**Returns:**

true Save successful 




**Returns:**

false Error saving 





        

<hr>

------------------------------
The documentation for this class was generated from the following file `C:/Users/jsime/OneDrive/Documents/Git/2025-Summer-Bot/src/argos_lib/include/argos_lib/homing/homing_interface.h`




# Class Debouncer



[**ClassList**](annotated.md) **>** [**Debouncer**](class_debouncer.md)



[More...](#detailed-description)






































## Public Functions

| Type | Name |
| ---: | :--- |
|   | [**Debouncer**](#function-debouncer-12) (const [**argos\_lib::DebounceSettings**](structargos__lib_1_1_debounce_settings.md) debounceSettings, bool initialValue=false) <br>_Construct a new_ [_**Debouncer**_](class_debouncer.md) _object with asymmetric times._ |
|   | [**Debouncer**](#function-debouncer-22) (const units::millisecond\_t symmetricDebounceTime) <br>_Construct a new_ [_**Debouncer**_](class_debouncer.md) _object with symmetric times._ |
|  bool | [**GetDebouncedStatus**](#function-getdebouncedstatus) () <br>_Retrieve latest debounced status._  |
|  bool | [**GetRawStatus**](#function-getrawstatus) () <br>_Retrieve latest raw status._  |
|  void | [**Reset**](#function-reset) (bool newVal) <br>_Resets debouncer to a known status like at construction._  |
|  bool | [**operator()**](#function-operator()) (bool newVal) <br>_Update debouncer with new input and retrieve latest debounced status._  |




























## Detailed Description




**Copyright:**

Copyright (c) Argos FRC Team 1756. Open Source Software; you can modify and/or share it under the terms of the license file in the root directory of this project. 





    
## Public Functions Documentation




### function Debouncer [1/2]

_Construct a new_ [_**Debouncer**_](class_debouncer.md) _object with asymmetric times._
```C++
explicit Debouncer::Debouncer (
    const argos_lib::DebounceSettings debounceSettings,
    bool initialValue=false
) 
```





**Parameters:**


* `debounceSettings` Configuration settings for activate and clear times 
* `initialValue` Initializes debouncer to this value 




        

<hr>



### function Debouncer [2/2]

_Construct a new_ [_**Debouncer**_](class_debouncer.md) _object with symmetric times._
```C++
explicit Debouncer::Debouncer (
    const units::millisecond_t symmetricDebounceTime
) 
```





**Parameters:**


* `symmetricDebounceTime` Symmetric activate and clear time 




        

<hr>



### function GetDebouncedStatus 

_Retrieve latest debounced status._ 
```C++
bool Debouncer::GetDebouncedStatus () 
```





**Returns:**

Value after applying debounce 





        

<hr>



### function GetRawStatus 

_Retrieve latest raw status._ 
```C++
bool Debouncer::GetRawStatus () 
```





**Returns:**

Latest value without applying debounce 





        

<hr>



### function Reset 

_Resets debouncer to a known status like at construction._ 
```C++
void Debouncer::Reset (
    bool newVal
) 
```





**Parameters:**


* `newVal` Value to set to 




        

<hr>



### function operator() 

_Update debouncer with new input and retrieve latest debounced status._ 
```C++
bool Debouncer::operator() (
    bool newVal
) 
```





**Parameters:**


* `newVal` Latest raw value 



**Returns:**

Value after applying debounce 





        

<hr>

------------------------------
The documentation for this class was generated from the following file `C:/Users/jsime/OneDrive/Documents/Git/2025-Summer-Bot/src/argos_lib/include/argos_lib/general/debouncer.h`


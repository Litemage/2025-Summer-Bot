

# Namespace argos\_lib::triggers



[**Namespace List**](namespaces.md) **>** [**argos\_lib**](namespaceargos__lib.md) **>** [**triggers**](namespaceargos__lib_1_1triggers.md)










































## Public Functions

| Type | Name |
| ---: | :--- |
|  frc2::Trigger | [**AllOf**](#function-allof) (std::vector&lt; frc2::Trigger &gt; triggers) <br>_Generates composite trigger that is true when all of the triggers are true._  |
|  frc2::Trigger | [**AnyOf**](#function-anyof) (std::vector&lt; frc2::Trigger &gt; triggers) <br>_Generates composite trigger that is true when any of the triggers is true._  |
|  frc2::Trigger | [**NoneOf**](#function-noneof) (std::vector&lt; frc2::Trigger &gt; triggers) <br>_Generates composite trigger that is true when none of the triggers is true._  |
|  frc2::Trigger | [**OneOf**](#function-oneof) (std::vector&lt; frc2::Trigger &gt; triggers) <br>_Generates composite trigger that is true when exactly one of the triggers is true._  |




























## Public Functions Documentation




### function AllOf 

_Generates composite trigger that is true when all of the triggers are true._ 
```C++
frc2::Trigger argos_lib::triggers::AllOf (
    std::vector< frc2::Trigger > triggers
) 
```





**Parameters:**


* `triggers` Triggers to check 



**Returns:**

frc2::Trigger Composite trigger 





        

<hr>



### function AnyOf 

_Generates composite trigger that is true when any of the triggers is true._ 
```C++
frc2::Trigger argos_lib::triggers::AnyOf (
    std::vector< frc2::Trigger > triggers
) 
```





**Parameters:**


* `triggers` Triggers to check 



**Returns:**

frc2::Trigger Composite trigger 





        

<hr>



### function NoneOf 

_Generates composite trigger that is true when none of the triggers is true._ 
```C++
frc2::Trigger argos_lib::triggers::NoneOf (
    std::vector< frc2::Trigger > triggers
) 
```





**Parameters:**


* `triggers` Triggers to check 



**Returns:**

frc2::Trigger Composite trigger 





        

<hr>



### function OneOf 

_Generates composite trigger that is true when exactly one of the triggers is true._ 
```C++
frc2::Trigger argos_lib::triggers::OneOf (
    std::vector< frc2::Trigger > triggers
) 
```





**Parameters:**


* `triggers` Triggers to check 



**Returns:**

frc2::Trigger Composite trigger 





        

<hr>

------------------------------
The documentation for this class was generated from the following file `C:/Users/jsime/OneDrive/Documents/Git/2025-Summer-Bot/src/argos_lib/include/argos_lib/controller/trigger_composition.h`


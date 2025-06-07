

# Struct argos\_lib::XboxController::UpdateStatus



[**ClassList**](annotated.md) **>** [**argos\_lib**](namespaceargos__lib.md) **>** [**XboxController**](classargos__lib_1_1_xbox_controller.md) **>** [**UpdateStatus**](structargos__lib_1_1_xbox_controller_1_1_update_status.md)



_State of an individual button._ 

* `#include <xbox_controller.h>`





















## Public Attributes

| Type | Name |
| ---: | :--- |
|  bool | [**debounceActive**](#variable-debounceactive)   = `false`<br>[_**Button**_](classargos__lib_1_1_xbox_controller.md#enum-button) _status after debounce applied._ |
|  bool | [**debouncePress**](#variable-debouncepress)   = `false`<br>_Transitioned from inactive to active after debounce applied._  |
|  bool | [**debounceRelease**](#variable-debouncerelease)   = `false`<br>_Transitioned from active to inactive after debounce applied._  |
|  bool | [**pressed**](#variable-pressed)   = `false`<br>_Transitioned from inactive to active._  |
|  bool | [**rawActive**](#variable-rawactive)   = `false`<br>_Raw button status._  |
|  bool | [**released**](#variable-released)   = `false`<br>_Transitioned from active to inactive._  |












































## Public Attributes Documentation




### variable debounceActive 

[_**Button**_](classargos__lib_1_1_xbox_controller.md#enum-button) _status after debounce applied._
```C++
bool argos_lib::XboxController::UpdateStatus::debounceActive;
```




<hr>



### variable debouncePress 

_Transitioned from inactive to active after debounce applied._ 
```C++
bool argos_lib::XboxController::UpdateStatus::debouncePress;
```




<hr>



### variable debounceRelease 

_Transitioned from active to inactive after debounce applied._ 
```C++
bool argos_lib::XboxController::UpdateStatus::debounceRelease;
```




<hr>



### variable pressed 

_Transitioned from inactive to active._ 
```C++
bool argos_lib::XboxController::UpdateStatus::pressed;
```




<hr>



### variable rawActive 

_Raw button status._ 
```C++
bool argos_lib::XboxController::UpdateStatus::rawActive;
```




<hr>



### variable released 

_Transitioned from active to inactive._ 
```C++
bool argos_lib::XboxController::UpdateStatus::released;
```




<hr>

------------------------------
The documentation for this class was generated from the following file `C:/Users/jsime/OneDrive/Documents/Git/2025-Summer-Bot/src/argos_lib/include/argos_lib/controller/xbox_controller.h`


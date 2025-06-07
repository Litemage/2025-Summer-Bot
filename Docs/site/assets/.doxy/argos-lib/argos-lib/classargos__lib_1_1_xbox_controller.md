

# Class argos\_lib::XboxController



[**ClassList**](annotated.md) **>** [**argos\_lib**](namespaceargos__lib.md) **>** [**XboxController**](classargos__lib_1_1_xbox_controller.md)








Inherits the following classes: frc::GenericHID












## Classes

| Type | Name |
| ---: | :--- |
| struct | [**UpdateStatus**](structargos__lib_1_1_xbox_controller_1_1_update_status.md) <br>_State of an individual button._  |


## Public Types

| Type | Name |
| ---: | :--- |
| enum  | [**Axis**](#enum-axis)  <br> |
| enum  | [**Button**](#enum-button)  <br> |
| enum  | [**JoystickHand**](#enum-joystickhand)  <br>_Replaces legacy joystick hand API for WPILib._  |




















## Public Functions

| Type | Name |
| ---: | :--- |
|  bool | [**GetDebouncedButton**](#function-getdebouncedbutton-12) ([**Button**](classargos__lib_1_1_xbox_controller.md#enum-button) buttonIdx) <br>_Get the status of button after applying debounce._  |
|  bool | [**GetDebouncedButton**](#function-getdebouncedbutton-22) (std::vector&lt; [**Button**](classargos__lib_1_1_xbox_controller.md#enum-button) &gt; buttonCombo) <br>_Get the status of a combination of buttons after applying debounce. Raw combo button state is active when all buttons are simultaneously active based on their independent debounce settings._  |
|  bool | [**GetDebouncedButtonPressed**](#function-getdebouncedbuttonpressed-12) ([**Button**](classargos__lib_1_1_xbox_controller.md#enum-button) buttonIdx) <br>_Detect if a button just transitioned from inactive to active after applying debounce._  |
|  bool | [**GetDebouncedButtonPressed**](#function-getdebouncedbuttonpressed-22) (std::vector&lt; [**Button**](classargos__lib_1_1_xbox_controller.md#enum-button) &gt; buttonCombo) <br>_Detect if a combination of buttons just transitioned from inactive to active after applying debounce. Raw combo button state is active when all buttons are simultaneously active based on their independent debounce settings._  |
|  bool | [**GetDebouncedButtonReleased**](#function-getdebouncedbuttonreleased-12) ([**Button**](classargos__lib_1_1_xbox_controller.md#enum-button) buttonIdx) <br>_Detect if a button just transitioned from active to inactive after applying debounce._  |
|  bool | [**GetDebouncedButtonReleased**](#function-getdebouncedbuttonreleased-22) (std::vector&lt; [**Button**](classargos__lib_1_1_xbox_controller.md#enum-button) &gt; buttonCombo) <br>_Detect if a combination of buttons just transitioned from active to inactive after applying debounce. Raw combo button state is active when all buttons are simultaneously active based on their independent debounce settings._  |
|  bool | [**GetRawButton**](#function-getrawbutton-12) ([**Button**](classargos__lib_1_1_xbox_controller.md#enum-button) buttonIdx) <br>_Get the status of button._  |
|  bool | [**GetRawButton**](#function-getrawbutton-22) (std::vector&lt; [**Button**](classargos__lib_1_1_xbox_controller.md#enum-button) &gt; buttonCombo) <br>_Get the status of a combination of buttons ignoring debounce. Raw combo button state is active when all buttons are simultaneously active._  |
|  bool | [**GetRawButtonPressed**](#function-getrawbuttonpressed-12) ([**Button**](classargos__lib_1_1_xbox_controller.md#enum-button) buttonIdx) <br>_Detect if a button just transitioned from inactive to active._  |
|  bool | [**GetRawButtonPressed**](#function-getrawbuttonpressed-22) (std::vector&lt; [**Button**](classargos__lib_1_1_xbox_controller.md#enum-button) &gt; buttonCombo) <br>_Detect if a combination of buttons just transitioned from inactive to active. Raw combo button state is active when all buttons are simultaneously active._  |
|  bool | [**GetRawButtonReleased**](#function-getrawbuttonreleased-12) ([**Button**](classargos__lib_1_1_xbox_controller.md#enum-button) buttonIdx) <br>_Detect if a button just transitioned from active to inactive._  |
|  bool | [**GetRawButtonReleased**](#function-getrawbuttonreleased-22) (std::vector&lt; [**Button**](classargos__lib_1_1_xbox_controller.md#enum-button) &gt; buttonCombo) <br>_Detect if a combination of buttons just transitioned from active to inactive. Raw combo button state is active when all buttons are simultaneously active._  |
|  double | [**GetTriggerAxis**](#function-gettriggeraxis) ([**JoystickHand**](classargos__lib_1_1_xbox_controller.md#enum-joystickhand) hand) const<br>_Get percent from specified controller trigger button._  |
|  VibrationModel | [**GetVibration**](#function-getvibration) () const<br>_Get the active vibration model._  |
|  double | [**GetX**](#function-getx) ([**JoystickHand**](classargos__lib_1_1_xbox_controller.md#enum-joystickhand) hand) const<br>_Get X joystick percent from specified joystick._  |
|  double | [**GetY**](#function-gety) ([**JoystickHand**](classargos__lib_1_1_xbox_controller.md#enum-joystickhand) hand) const<br>_Get Y joystick percent from specified joystick._  |
|  void | [**SetButtonDebounce**](#function-setbuttondebounce) ([**Button**](classargos__lib_1_1_xbox_controller.md#enum-button) targetButton, [**DebounceSettings**](structargos__lib_1_1_debounce_settings.md) newSettings) <br>_Configure debounce for a specified button._  |
|  void | [**SetVibration**](#function-setvibration) (VibrationModel newVibrationModel) <br>_Sets a new vibration pattern and updates vibration output based on that new model._  |
|  void | [**SwapSettings**](#function-swapsettings) ([**XboxController**](classargos__lib_1_1_xbox_controller.md) & other) <br>_Swap all configurations (debounce, etc) between this and other controller. Useful in conjunction with_ [_**argos\_lib::SwappableControllersSubsystem**_](classargos__lib_1_1_swappable_controllers_subsystem.md) _._ |
|  frc2::Trigger | [**TriggerDebounced**](#function-triggerdebounced-12) ([**Button**](classargos__lib_1_1_xbox_controller.md#enum-button) button) <br>_Generates a trigger that is true when debounced button is true._  |
|  frc2::Trigger | [**TriggerDebounced**](#function-triggerdebounced-22) (std::vector&lt; [**Button**](classargos__lib_1_1_xbox_controller.md#enum-button) &gt; buttonCombo) <br>_Generates a trigger that is true when all debounced buttons in buttonCombo are true._  |
|  frc2::Trigger | [**TriggerDebouncedAllOf**](#function-triggerdebouncedallof) (std::vector&lt; [**Button**](classargos__lib_1_1_xbox_controller.md#enum-button) &gt; buttonCombo) <br>_Trigger when all of the selected buttons' debounced values are true._  |
|  frc2::Trigger | [**TriggerDebouncedAnyOf**](#function-triggerdebouncedanyof) (std::vector&lt; [**Button**](classargos__lib_1_1_xbox_controller.md#enum-button) &gt; buttonCombo) <br>_Trigger when any of the selected buttons' debounced value is true._  |
|  frc2::Trigger | [**TriggerDebouncedNoneOf**](#function-triggerdebouncednoneof) (std::vector&lt; [**Button**](classargos__lib_1_1_xbox_controller.md#enum-button) &gt; buttonCombo) <br>_Trigger when none of the selected buttons' debounced value is true._  |
|  frc2::Trigger | [**TriggerDebouncedOneOf**](#function-triggerdebouncedoneof) (std::vector&lt; [**Button**](classargos__lib_1_1_xbox_controller.md#enum-button) &gt; buttonCombo) <br>_Trigger when exactly one of the selected buttons' debounced value is true._  |
|  frc2::Trigger | [**TriggerRaw**](#function-triggerraw-12) ([**Button**](classargos__lib_1_1_xbox_controller.md#enum-button) button) <br>_Generates a trigger that is true when button is true._  |
|  frc2::Trigger | [**TriggerRaw**](#function-triggerraw-22) (std::vector&lt; [**Button**](classargos__lib_1_1_xbox_controller.md#enum-button) &gt; buttonCombo) <br>_Generates a trigger that is true when all buttons in buttonCombo are true._  |
|  frc2::Trigger | [**TriggerRawAllOf**](#function-triggerrawallof) (std::vector&lt; [**Button**](classargos__lib_1_1_xbox_controller.md#enum-button) &gt; buttonCombo) <br>_Trigger when all of the selected buttons' raw values are true._  |
|  frc2::Trigger | [**TriggerRawAnyOf**](#function-triggerrawanyof) (std::vector&lt; [**Button**](classargos__lib_1_1_xbox_controller.md#enum-button) &gt; buttonCombo) <br>_Trigger when any of the selected buttons' raw value is true._  |
|  frc2::Trigger | [**TriggerRawNoneOf**](#function-triggerrawnoneof) (std::vector&lt; [**Button**](classargos__lib_1_1_xbox_controller.md#enum-button) &gt; buttonCombo) <br>_Trigger when none of the selected buttons' raw value is true._  |
|  frc2::Trigger | [**TriggerRawOneOf**](#function-triggerrawoneof) (std::vector&lt; [**Button**](classargos__lib_1_1_xbox_controller.md#enum-button) &gt; buttonCombo) <br>_Trigger when exactly one of the selected buttons' raw value is true._  |
|  [**UpdateStatus**](structargos__lib_1_1_xbox_controller_1_1_update_status.md) | [**UpdateButton**](#function-updatebutton) ([**Button**](classargos__lib_1_1_xbox_controller.md#enum-button) buttonIdx) <br>_Determines the new status of a button. This is used by the other status retrieval functions._  |
|  void | [**UpdateVibration**](#function-updatevibration) () <br>_Update vibration output based on current vibration model._  |
|   | [**XboxController**](#function-xboxcontroller-12) () = delete<br> |
|   | [**XboxController**](#function-xboxcontroller-22) (int port) <br>_Construct a new Xbox Controller object connected at port index._  |




























## Public Types Documentation




### enum Axis 

```C++
enum argos_lib::XboxController::Axis {
    kLeftX = 0,
    kLeftY = 1,
    kLeftTrigger = 2,
    kRightTrigger = 3,
    kRightX = 4,
    kRightY = 5,
    COUNT
};
```




<hr>



### enum Button 

```C++
enum argos_lib::XboxController::Button {
    kA = 1,
    kB = 2,
    kX = 3,
    kY = 4,
    kBumperLeft = 5,
    kBumperRight = 6,
    kBack = 7,
    kStart = 8,
    kStickLeft = 9,
    kStickRight = 10,
    kLeftTrigger = 11,
    kRightTrigger = 12,
    kUp = 13,
    kRight = 14,
    kDown = 15,
    kLeft = 16,
    COUNT
};
```




<hr>



### enum JoystickHand 

_Replaces legacy joystick hand API for WPILib._ 
```C++
enum argos_lib::XboxController::JoystickHand {
    kLeftHand,
    kRightHand
};
```




<hr>
## Public Functions Documentation




### function GetDebouncedButton [1/2]

_Get the status of button after applying debounce._ 
```C++
bool argos_lib::XboxController::GetDebouncedButton (
    Button buttonIdx
) 
```





**Parameters:**


* `buttonIdx` Index of requested button 



**Returns:**

debounced status 





        

<hr>



### function GetDebouncedButton [2/2]

_Get the status of a combination of buttons after applying debounce. Raw combo button state is active when all buttons are simultaneously active based on their independent debounce settings._ 
```C++
bool argos_lib::XboxController::GetDebouncedButton (
    std::vector< Button > buttonCombo
) 
```





**Parameters:**


* `buttonCombo` Buttons that make up the combination 



**Returns:**

debounced status 





        

<hr>



### function GetDebouncedButtonPressed [1/2]

_Detect if a button just transitioned from inactive to active after applying debounce._ 
```C++
bool argos_lib::XboxController::GetDebouncedButtonPressed (
    Button buttonIdx
) 
```





**Parameters:**


* `buttonIdx` Index of requested button 



**Returns:**

true if inactive to active transition occurred 





        

<hr>



### function GetDebouncedButtonPressed [2/2]

_Detect if a combination of buttons just transitioned from inactive to active after applying debounce. Raw combo button state is active when all buttons are simultaneously active based on their independent debounce settings._ 
```C++
bool argos_lib::XboxController::GetDebouncedButtonPressed (
    std::vector< Button > buttonCombo
) 
```





**Parameters:**


* `buttonCombo` Buttons that make up the combination 



**Returns:**

true if combination transition to active occurred 





        

<hr>



### function GetDebouncedButtonReleased [1/2]

_Detect if a button just transitioned from active to inactive after applying debounce._ 
```C++
bool argos_lib::XboxController::GetDebouncedButtonReleased (
    Button buttonIdx
) 
```





**Parameters:**


* `buttonIdx` Index of requested button 



**Returns:**

true if active to inactive transition occurred 





        

<hr>



### function GetDebouncedButtonReleased [2/2]

_Detect if a combination of buttons just transitioned from active to inactive after applying debounce. Raw combo button state is active when all buttons are simultaneously active based on their independent debounce settings._ 
```C++
bool argos_lib::XboxController::GetDebouncedButtonReleased (
    std::vector< Button > buttonCombo
) 
```





**Parameters:**


* `buttonCombo` Buttons that make up the combination 



**Returns:**

true if combination transition to inactive occurred 





        

<hr>



### function GetRawButton [1/2]

_Get the status of button._ 
```C++
bool argos_lib::XboxController::GetRawButton (
    Button buttonIdx
) 
```





**Parameters:**


* `buttonIdx` Index of requested button 



**Returns:**

Status ignoring any debounce 





        

<hr>



### function GetRawButton [2/2]

_Get the status of a combination of buttons ignoring debounce. Raw combo button state is active when all buttons are simultaneously active._ 
```C++
bool argos_lib::XboxController::GetRawButton (
    std::vector< Button > buttonCombo
) 
```





**Parameters:**


* `buttonCombo` Buttons that make up the combination 



**Returns:**

Status ignoring any debounce 





        

<hr>



### function GetRawButtonPressed [1/2]

_Detect if a button just transitioned from inactive to active._ 
```C++
bool argos_lib::XboxController::GetRawButtonPressed (
    Button buttonIdx
) 
```





**Parameters:**


* `buttonIdx` Index of requested button 



**Returns:**

true if inactive to active transition occurred 





        

<hr>



### function GetRawButtonPressed [2/2]

_Detect if a combination of buttons just transitioned from inactive to active. Raw combo button state is active when all buttons are simultaneously active._ 
```C++
bool argos_lib::XboxController::GetRawButtonPressed (
    std::vector< Button > buttonCombo
) 
```





**Parameters:**


* `buttonCombo` Buttons that make up the combination 



**Returns:**

true if combination transition to active occurred 





        

<hr>



### function GetRawButtonReleased [1/2]

_Detect if a button just transitioned from active to inactive._ 
```C++
bool argos_lib::XboxController::GetRawButtonReleased (
    Button buttonIdx
) 
```





**Parameters:**


* `buttonIdx` Index of requested button 



**Returns:**

true if active to inactive transition occurred 





        

<hr>



### function GetRawButtonReleased [2/2]

_Detect if a combination of buttons just transitioned from active to inactive. Raw combo button state is active when all buttons are simultaneously active._ 
```C++
bool argos_lib::XboxController::GetRawButtonReleased (
    std::vector< Button > buttonCombo
) 
```





**Parameters:**


* `buttonCombo` Buttons that make up the combination 



**Returns:**

true if combination transition to inactive occurred 





        

<hr>



### function GetTriggerAxis 

_Get percent from specified controller trigger button._ 
```C++
double argos_lib::XboxController::GetTriggerAxis (
    JoystickHand hand
) const
```





**Parameters:**


* `hand` Left or right trigger 



**Returns:**

double Percent [0,1] 





        

<hr>



### function GetVibration 

_Get the active vibration model._ 
```C++
VibrationModel argos_lib::XboxController::GetVibration () const
```





**Returns:**

Active vibration model 





        

<hr>



### function GetX 

_Get X joystick percent from specified joystick._ 
```C++
double argos_lib::XboxController::GetX (
    JoystickHand hand
) const
```





**Parameters:**


* `hand` Left or right joystick 



**Returns:**

double Percent [-1,1] 





        

<hr>



### function GetY 

_Get Y joystick percent from specified joystick._ 
```C++
double argos_lib::XboxController::GetY (
    JoystickHand hand
) const
```





**Parameters:**


* `hand` Left or right joystick 



**Returns:**

double Percent [-1,1] 





        

<hr>



### function SetButtonDebounce 

_Configure debounce for a specified button._ 
```C++
void argos_lib::XboxController::SetButtonDebounce (
    Button targetButton,
    DebounceSettings newSettings
) 
```





**Parameters:**


* `targetButton` [**Button**](classargos__lib_1_1_xbox_controller.md#enum-button) to configure 
* `newSettings` New debounce configuration 




        

<hr>



### function SetVibration 

_Sets a new vibration pattern and updates vibration output based on that new model._ 
```C++
void argos_lib::XboxController::SetVibration (
    VibrationModel newVibrationModel
) 
```





**Parameters:**


* `newVibrationModel` Model to generate vibration output 




        

<hr>



### function SwapSettings 

_Swap all configurations (debounce, etc) between this and other controller. Useful in conjunction with_ [_**argos\_lib::SwappableControllersSubsystem**_](classargos__lib_1_1_swappable_controllers_subsystem.md) _._
```C++
void argos_lib::XboxController::SwapSettings (
    XboxController & other
) 
```





**Parameters:**


* `other` Controller to swap settings with 




        

<hr>



### function TriggerDebounced [1/2]

_Generates a trigger that is true when debounced button is true._ 
```C++
frc2::Trigger argos_lib::XboxController::TriggerDebounced (
    Button button
) 
```





**Parameters:**


* `button` [**Button**](classargos__lib_1_1_xbox_controller.md#enum-button) to monitor 



**Returns:**

frc2::Trigger Trigger to monitor debounced button 





        

<hr>



### function TriggerDebounced [2/2]

_Generates a trigger that is true when all debounced buttons in buttonCombo are true._ 
```C++
frc2::Trigger argos_lib::XboxController::TriggerDebounced (
    std::vector< Button > buttonCombo
) 
```





**Parameters:**


* `buttonCombo` Buttons to monitor 



**Returns:**

frc2::Trigger Trigger to monitor debounced buttons 





        

<hr>



### function TriggerDebouncedAllOf 

_Trigger when all of the selected buttons' debounced values are true._ 
```C++
frc2::Trigger argos_lib::XboxController::TriggerDebouncedAllOf (
    std::vector< Button > buttonCombo
) 
```





**Parameters:**


* `buttonCombo` Buttons to check 



**Returns:**

frc2::Trigger Trigger indicating all button debounced values are true 





        

<hr>



### function TriggerDebouncedAnyOf 

_Trigger when any of the selected buttons' debounced value is true._ 
```C++
frc2::Trigger argos_lib::XboxController::TriggerDebouncedAnyOf (
    std::vector< Button > buttonCombo
) 
```





**Parameters:**


* `buttonCombo` Buttons to check 



**Returns:**

frc2::Trigger Trigger indicating any button debounced value is true 





        

<hr>



### function TriggerDebouncedNoneOf 

_Trigger when none of the selected buttons' debounced value is true._ 
```C++
frc2::Trigger argos_lib::XboxController::TriggerDebouncedNoneOf (
    std::vector< Button > buttonCombo
) 
```





**Parameters:**


* `buttonCombo` Buttons to check 



**Returns:**

frc2::Trigger Trigger indicating none button debounced value is true 





        

<hr>



### function TriggerDebouncedOneOf 

_Trigger when exactly one of the selected buttons' debounced value is true._ 
```C++
frc2::Trigger argos_lib::XboxController::TriggerDebouncedOneOf (
    std::vector< Button > buttonCombo
) 
```





**Parameters:**


* `buttonCombo` Buttons to check 



**Returns:**

frc2::Trigger Trigger indicating one button's debounced value is true 





        

<hr>



### function TriggerRaw [1/2]

_Generates a trigger that is true when button is true._ 
```C++
frc2::Trigger argos_lib::XboxController::TriggerRaw (
    Button button
) 
```





**Parameters:**


* `button` [**Button**](classargos__lib_1_1_xbox_controller.md#enum-button) to monitor 



**Returns:**

frc2::Trigger Trigger to monitor button 





        

<hr>



### function TriggerRaw [2/2]

_Generates a trigger that is true when all buttons in buttonCombo are true._ 
```C++
frc2::Trigger argos_lib::XboxController::TriggerRaw (
    std::vector< Button > buttonCombo
) 
```





**Parameters:**


* `buttonCombo` Buttons to monitor 



**Returns:**

frc2::Trigger Trigger to monitor buttons 





        

<hr>



### function TriggerRawAllOf 

_Trigger when all of the selected buttons' raw values are true._ 
```C++
frc2::Trigger argos_lib::XboxController::TriggerRawAllOf (
    std::vector< Button > buttonCombo
) 
```





**Parameters:**


* `buttonCombo` Buttons to check 



**Returns:**

frc2::Trigger Trigger indicating all button raw values are true 





        

<hr>



### function TriggerRawAnyOf 

_Trigger when any of the selected buttons' raw value is true._ 
```C++
frc2::Trigger argos_lib::XboxController::TriggerRawAnyOf (
    std::vector< Button > buttonCombo
) 
```





**Parameters:**


* `buttonCombo` Buttons to check 



**Returns:**

frc2::Trigger Trigger indicating any button raw value is true 





        

<hr>



### function TriggerRawNoneOf 

_Trigger when none of the selected buttons' raw value is true._ 
```C++
frc2::Trigger argos_lib::XboxController::TriggerRawNoneOf (
    std::vector< Button > buttonCombo
) 
```





**Parameters:**


* `buttonCombo` Buttons to check 



**Returns:**

frc2::Trigger Trigger indicating none button raw value is true 





        

<hr>



### function TriggerRawOneOf 

_Trigger when exactly one of the selected buttons' raw value is true._ 
```C++
frc2::Trigger argos_lib::XboxController::TriggerRawOneOf (
    std::vector< Button > buttonCombo
) 
```





**Parameters:**


* `buttonCombo` Buttons to check 



**Returns:**

frc2::Trigger Trigger indicating one button's raw value is true 





        

<hr>



### function UpdateButton 

_Determines the new status of a button. This is used by the other status retrieval functions._ 
```C++
UpdateStatus argos_lib::XboxController::UpdateButton (
    Button buttonIdx
) 
```





**Parameters:**


* `buttonIdx` Index of button to update 



**Returns:**

[**UpdateStatus**](structargos__lib_1_1_xbox_controller_1_1_update_status.md) Full button state 





        

<hr>



### function UpdateVibration 

_Update vibration output based on current vibration model._ 
```C++
void argos_lib::XboxController::UpdateVibration () 
```




<hr>



### function XboxController [1/2]

```C++
argos_lib::XboxController::XboxController () = delete
```




<hr>



### function XboxController [2/2]

_Construct a new Xbox Controller object connected at port index._ 
```C++
explicit argos_lib::XboxController::XboxController (
    int port
) 
```





**Parameters:**


* `port` Index of new controller 




        

<hr>

------------------------------
The documentation for this class was generated from the following file `C:/Users/jsime/OneDrive/Documents/Git/2025-Summer-Bot/src/argos_lib/include/argos_lib/controller/xbox_controller.h`


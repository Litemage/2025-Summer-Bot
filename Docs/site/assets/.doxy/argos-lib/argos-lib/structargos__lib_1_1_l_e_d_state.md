

# Struct argos\_lib::LEDState



[**ClassList**](annotated.md) **>** [**argos\_lib**](namespaceargos__lib.md) **>** [**LEDState**](structargos__lib_1_1_l_e_d_state.md)



_Color and animation status for an individual LED._ 

* `#include <led_subsystem.h>`





















## Public Attributes

| Type | Name |
| ---: | :--- |
|  bool | [**animated**](#variable-animated)   = `{false}`<br>_True indicates this is using a stock animation._  |
|  frc::AddressableLED::LEDData | [**color**](#variable-color)  <br>_Color of LED. Only used when animated is false._  |
















## Public Functions

| Type | Name |
| ---: | :--- |
|  bool | [**operator!=**](#function-operator) (const [**LEDState**](structargos__lib_1_1_l_e_d_state.md) & other) const<br>_It's an inequality comparison operator..._  |
|  [**LEDState**](structargos__lib_1_1_l_e_d_state.md) & | [**operator=**](#function-operator_1) (const frc::AddressableLED::LEDData & other) <br>_Copy assignment operator._  |
|  bool | [**operator==**](#function-operator_2) (const [**LEDState**](structargos__lib_1_1_l_e_d_state.md) & other) const<br>_It's an equality comparison operator..._  |




























## Public Attributes Documentation




### variable animated 

_True indicates this is using a stock animation._ 
```C++
bool argos_lib::LEDState::animated;
```




<hr>



### variable color 

_Color of LED. Only used when animated is false._ 
```C++
frc::AddressableLED::LEDData argos_lib::LEDState::color;
```




<hr>
## Public Functions Documentation




### function operator!= 

_It's an inequality comparison operator..._ 
```C++
bool argos_lib::LEDState::operator!= (
    const LEDState & other
) const
```





**Parameters:**


* `other` [**LEDState**](structargos__lib_1_1_l_e_d_state.md) to compare to 



**Returns:**

True when states are different 





        

<hr>



### function operator= 

_Copy assignment operator._ 
```C++
LEDState & argos_lib::LEDState::operator= (
    const frc::AddressableLED::LEDData & other
) 
```





**Parameters:**


* `other` New value to assign to self 



**Returns:**

[**LEDState**](structargos__lib_1_1_l_e_d_state.md)& Reference to this object after assignment 





        

<hr>



### function operator== 

_It's an equality comparison operator..._ 
```C++
bool argos_lib::LEDState::operator== (
    const LEDState & other
) const
```





**Parameters:**


* `other` [**LEDState**](structargos__lib_1_1_l_e_d_state.md) to compare to 



**Returns:**

True when both states are equivalent 





        

<hr>

------------------------------
The documentation for this class was generated from the following file `C:/Users/jsime/OneDrive/Documents/Git/2025-Summer-Bot/src/argos_lib/include/argos_lib/subsystems/led_subsystem.h`


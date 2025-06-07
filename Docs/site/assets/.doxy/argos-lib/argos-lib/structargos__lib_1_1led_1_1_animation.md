

# Struct argos\_lib::led::Animation



[**ClassList**](annotated.md) **>** [**argos\_lib**](namespaceargos__lib.md) **>** [**led**](namespaceargos__lib_1_1led.md) **>** [**Animation**](structargos__lib_1_1led_1_1_animation.md)



_A representation of a custom LED animation._ 

* `#include <animiation.h>`





















## Public Attributes

| Type | Name |
| ---: | :--- |
|  unsigned | [**numLEDs**](#variable-numleds)  <br>_Number of LEDs in the animation._  |
|  unsigned | [**offset**](#variable-offset)  <br>_Address of first LED._  |
|  std::function&lt; Strip()&gt; | [**update**](#variable-update)  <br>_This function can be any callable that returns a sequence of LED colors._  |
















## Public Functions

| Type | Name |
| ---: | :--- |
|   | [**Animation**](#function-animation-12) () = delete<br>_Delete default constructor because it is meaningless._  |
|   | [**Animation**](#function-animation-22) (std::function&lt; Strip()&gt; update, unsigned numLEDs, unsigned offset) <br>_Construct a new_ [_**Animation**_](structargos__lib_1_1led_1_1_animation.md) _object._ |




























## Public Attributes Documentation




### variable numLEDs 

_Number of LEDs in the animation._ 
```C++
unsigned argos_lib::led::Animation::numLEDs;
```




<hr>



### variable offset 

_Address of first LED._ 
```C++
unsigned argos_lib::led::Animation::offset;
```




<hr>



### variable update 

_This function can be any callable that returns a sequence of LED colors._ 
```C++
std::function<Strip()> argos_lib::led::Animation::update;
```




<hr>
## Public Functions Documentation




### function Animation [1/2]

_Delete default constructor because it is meaningless._ 
```C++
argos_lib::led::Animation::Animation () = delete
```




<hr>



### function Animation [2/2]

_Construct a new_ [_**Animation**_](structargos__lib_1_1led_1_1_animation.md) _object._
```C++
inline argos_lib::led::Animation::Animation (
    std::function< Strip()> update,
    unsigned numLEDs,
    unsigned offset
) 
```





**Parameters:**


* `update` Function to call that generates the new LED states for this animation 
* `numLEDs` Number of LEDs in the animation 
* `offset` Address of first LED controlled by this animation 




        

<hr>

------------------------------
The documentation for this class was generated from the following file `C:/Users/jsime/OneDrive/Documents/Git/2025-Summer-Bot/src/argos_lib/include/argos_lib/led/animiation.h`


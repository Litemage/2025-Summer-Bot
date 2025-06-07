

# Struct argos\_lib::LEDSubsystem::LEDUpdateGroup



[**ClassList**](annotated.md) **>** [**LEDUpdateGroup**](structargos__lib_1_1_l_e_d_subsystem_1_1_l_e_d_update_group.md)



_Represents a contiguous block of LEDs that have the same color._ 






















## Public Attributes

| Type | Name |
| ---: | :--- |
|  frc::AddressableLED::LEDData | [**color**](#variable-color)  <br>_Color of LEDs._  |
|  unsigned | [**numLEDs**](#variable-numleds)  <br>_Number of LEDs in group._  |
|  unsigned | [**startIndex**](#variable-startindex)  <br>_Address of first LED._  |
















## Public Functions

| Type | Name |
| ---: | :--- |
|   | [**LEDUpdateGroup**](#function-ledupdategroup) (unsigned startIndex, unsigned numLEDs, frc::AddressableLED::LEDData color) <br>_Construct a new LEDUpdateGroup with specified color._  |




























## Public Attributes Documentation




### variable color 

_Color of LEDs._ 
```C++
frc::AddressableLED::LEDData argos_lib::LEDSubsystem::LEDUpdateGroup::color;
```




<hr>



### variable numLEDs 

_Number of LEDs in group._ 
```C++
unsigned argos_lib::LEDSubsystem::LEDUpdateGroup::numLEDs;
```




<hr>



### variable startIndex 

_Address of first LED._ 
```C++
unsigned argos_lib::LEDSubsystem::LEDUpdateGroup::startIndex;
```




<hr>
## Public Functions Documentation




### function LEDUpdateGroup 

_Construct a new LEDUpdateGroup with specified color._ 
```C++
inline LEDUpdateGroup::LEDUpdateGroup (
    unsigned startIndex,
    unsigned numLEDs,
    frc::AddressableLED::LEDData color
) 
```





**Parameters:**


* `startIndex` Address of first LED in group 
* `numLEDs` Number of LEDs in group 
* `color` Color of LEDs in group 




        

<hr>

------------------------------
The documentation for this class was generated from the following file `C:/Users/jsime/OneDrive/Documents/Git/2025-Summer-Bot/src/argos_lib/include/argos_lib/subsystems/led_subsystem.h`


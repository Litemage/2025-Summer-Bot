

# Class argos\_lib::LEDSubsystem



[**ClassList**](annotated.md) **>** [**argos\_lib**](namespaceargos__lib.md) **>** [**LEDSubsystem**](classargos__lib_1_1_l_e_d_subsystem.md)








Inherits the following classes: frc2::SubsystemBase


































## Public Functions

| Type | Name |
| ---: | :--- |
|  void | [**CustomAnimateAuxLEDs**](#function-customanimateauxleds) ([**argos\_lib::led::Animation**](structargos__lib_1_1led_1_1_animation.md) animation) <br>_Set LEDs in attached strip/panel to use custom animation. The LEDs will be updated on every call of the subsystem periodic function._  |
|  void | [**CustomAnimateIntegratedLEDs**](#function-customanimateintegratedleds) ([**argos\_lib::led::Animation**](structargos__lib_1_1led_1_1_animation.md) animation) <br>_Set LEDs built into CANdle to use custom animation. The LEDs will be updated on every call of the subsystem periodic function._  |
|   | [**LEDSubsystem**](#function-ledsubsystem) (unsigned numAuxLEDs) <br>_Construct a new_ [_**LEDSubsystem**_](classargos__lib_1_1_l_e_d_subsystem.md) _object._ |
|  void | [**Periodic**](#function-periodic) () override<br> |
|  void | [**StockAnimateAuxLEDs**](#function-stockanimateauxleds) (ctre::phoenix::led::Animation & animation, int slot) <br>_Set LEDs in attached strip/panel to use stock animation._  |
|  void | [**StockAnimateIntegratedLEDs**](#function-stockanimateintegratedleds) (ctre::phoenix::led::Animation & animation, int slot) <br>_Set LEDs built into CANdle to use stock animation._  |




























## Public Functions Documentation




### function CustomAnimateAuxLEDs 

_Set LEDs in attached strip/panel to use custom animation. The LEDs will be updated on every call of the subsystem periodic function._ 
```C++
void argos_lib::LEDSubsystem::CustomAnimateAuxLEDs (
    argos_lib::led::Animation animation
) 
```





**Parameters:**


* `animation` Animation to use where led offset 0 is beginning of attached LEDs 




        

<hr>



### function CustomAnimateIntegratedLEDs 

_Set LEDs built into CANdle to use custom animation. The LEDs will be updated on every call of the subsystem periodic function._ 
```C++
void argos_lib::LEDSubsystem::CustomAnimateIntegratedLEDs (
    argos_lib::led::Animation animation
) 
```





**Parameters:**


* `animation` Animation to use 




        

<hr>



### function LEDSubsystem 

_Construct a new_ [_**LEDSubsystem**_](classargos__lib_1_1_l_e_d_subsystem.md) _object._
```C++
explicit argos_lib::LEDSubsystem::LEDSubsystem (
    unsigned numAuxLEDs
) 
```





**Parameters:**


* `numAuxLEDs` Number of LEDs attached to the CANdle 




        

<hr>



### function Periodic 

```C++
void argos_lib::LEDSubsystem::Periodic () override
```



Will be called periodically whenever the CommandScheduler runs. 


        

<hr>



### function StockAnimateAuxLEDs 

_Set LEDs in attached strip/panel to use stock animation._ 
```C++
void argos_lib::LEDSubsystem::StockAnimateAuxLEDs (
    ctre::phoenix::led::Animation & animation,
    int slot
) 
```





**Parameters:**


* `animation` Animation to assign where led offset 0 is beginning of attached LEDs 
* `slot` Animation slot to use 




        

<hr>



### function StockAnimateIntegratedLEDs 

_Set LEDs built into CANdle to use stock animation._ 
```C++
void argos_lib::LEDSubsystem::StockAnimateIntegratedLEDs (
    ctre::phoenix::led::Animation & animation,
    int slot
) 
```





**Parameters:**


* `animation` Animation to assign 
* `slot` Animation slot to use 




        

<hr>

------------------------------
The documentation for this class was generated from the following file `C:/Users/jsime/OneDrive/Documents/Git/2025-Summer-Bot/src/argos_lib/include/argos_lib/subsystems/led_subsystem.h`


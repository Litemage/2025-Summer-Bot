

# Class argos\_lib::SwapControllersCommand



[**ClassList**](annotated.md) **>** [**argos\_lib**](namespaceargos__lib.md) **>** [**SwapControllersCommand**](classargos__lib_1_1_swap_controllers_command.md)



_Swaps rolls of two controllers. Useful if one controller breaks during a match._ 

* `#include <swap_controllers_command.h>`



Inherits the following classes: frc2::CommandHelper< frc2::Command, SwapControllersCommand >


































## Public Functions

| Type | Name |
| ---: | :--- |
|  void | [**End**](#function-end) (bool) override<br>_Swap controllers when trigger ends._  |
|  void | [**Initialize**](#function-initialize) () override<br>_Indicate swap has started, but don't actually swap yet._  |
|   | [**SwapControllersCommand**](#function-swapcontrollerscommand) ([**SwappableControllersSubsystem**](classargos__lib_1_1_swappable_controllers_subsystem.md) \* controllers) <br> |




























## Public Functions Documentation




### function End 

_Swap controllers when trigger ends._ 
```C++
void argos_lib::SwapControllersCommand::End (
    bool
) override
```




<hr>



### function Initialize 

_Indicate swap has started, but don't actually swap yet._ 
```C++
void argos_lib::SwapControllersCommand::Initialize () override
```




<hr>



### function SwapControllersCommand 

```C++
explicit argos_lib::SwapControllersCommand::SwapControllersCommand (
    SwappableControllersSubsystem * controllers
) 
```




<hr>

------------------------------
The documentation for this class was generated from the following file `C:/Users/jsime/OneDrive/Documents/Git/2025-Summer-Bot/src/argos_lib/include/argos_lib/commands/swap_controllers_command.h`


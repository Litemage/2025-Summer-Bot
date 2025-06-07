

# Class argos\_lib::InterpolationMap

**template &lt;class T, int size, class V&gt;**



[**ClassList**](annotated.md) **>** [**argos\_lib**](namespaceargos__lib.md) **>** [**InterpolationMap**](classargos__lib_1_1_interpolation_map.md)



_Performs linear interpolation of a value based on a set of input-&gt;output mapping points._ [More...](#detailed-description)

* `#include <interpolation.h>`





































## Public Functions

| Type | Name |
| ---: | :--- |
|   | [**InterpolationMap**](#function-interpolationmap-12) () = delete<br> |
|  constexpr | [**InterpolationMap**](#function-interpolationmap-22) (std::array&lt; [**InterpMapPoint**](structargos__lib_1_1_interp_map_point.md)&lt; T, V &gt;, size &gt; initArray) <br>_Constructs new interpolation map._  |
|  V | [**Map**](#function-map) (const T inVal) const<br>_Generate interpolated output based on input._  |
|  V | [**operator()**](#function-operator()) (const T inVal) const<br>_Generate interpolated output based on input._  |




























## Detailed Description




**Template parameters:**


* `T` Type of interpolated input 
* `size` Number of elements in interpolation map 
* `V` Type of interpolated output 




    
## Public Functions Documentation




### function InterpolationMap [1/2]

```C++
argos_lib::InterpolationMap::InterpolationMap () = delete
```




<hr>



### function InterpolationMap [2/2]

_Constructs new interpolation map._ 
```C++
inline constexpr argos_lib::InterpolationMap::InterpolationMap (
    std::array< InterpMapPoint < T, V >, size > initArray
) 
```





**Parameters:**


* `initArray` Interpolation points. Must be sorted by input value with smallest element first. 




        

<hr>



### function Map 

_Generate interpolated output based on input._ 
```C++
inline V argos_lib::InterpolationMap::Map (
    const T inVal
) const
```





**Parameters:**


* `inVal` Input value to remap 



**Returns:**

Interpolated value 





        

<hr>



### function operator() 

_Generate interpolated output based on input._ 
```C++
inline V argos_lib::InterpolationMap::operator() (
    const T inVal
) const
```





**Parameters:**


* `inVal` Input value to remap 



**Returns:**

Interpolated value   


Shorthand for [**InterpolationMap::Map()**](classargos__lib_1_1_interpolation_map.md#function-map) 


        

<hr>

------------------------------
The documentation for this class was generated from the following file `C:/Users/jsime/OneDrive/Documents/Git/2025-Summer-Bot/src/argos_lib/include/argos_lib/general/interpolation.h`


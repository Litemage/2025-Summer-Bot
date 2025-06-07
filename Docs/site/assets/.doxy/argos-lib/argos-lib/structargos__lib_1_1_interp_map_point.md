

# Struct argos\_lib::InterpMapPoint

**template &lt;class T, class V&gt;**



[**ClassList**](annotated.md) **>** [**argos\_lib**](namespaceargos__lib.md) **>** [**InterpMapPoint**](structargos__lib_1_1_interp_map_point.md)



_Point that helps generate an interpolation map._ [More...](#detailed-description)

* `#include <interpolation.h>`





















## Public Attributes

| Type | Name |
| ---: | :--- |
|  T | [**inVal**](#variable-inval)  <br> |
|  V | [**outVal**](#variable-outval)  <br> |
















## Public Functions

| Type | Name |
| ---: | :--- |
|  constexpr | [**InterpMapPoint**](#function-interpmappoint) (T in, V out) <br> |
|  bool | [**operator&lt;**](#function-operator) (const [**InterpMapPoint**](structargos__lib_1_1_interp_map_point.md)&lt; T, V &gt; & other) <br> |
|  bool | [**operator==**](#function-operator_1) (const [**InterpMapPoint**](structargos__lib_1_1_interp_map_point.md)&lt; T, V &gt; & other) <br> |




























## Detailed Description




**Template parameters:**


* `T` Internal type. Typically float or double 




    
## Public Attributes Documentation




### variable inVal 

```C++
T argos_lib::InterpMapPoint< T, V >::inVal;
```




<hr>



### variable outVal 

```C++
V argos_lib::InterpMapPoint< T, V >::outVal;
```




<hr>
## Public Functions Documentation




### function InterpMapPoint 

```C++
inline constexpr argos_lib::InterpMapPoint::InterpMapPoint (
    T in,
    V out
) 
```




<hr>



### function operator&lt; 

```C++
inline bool argos_lib::InterpMapPoint::operator< (
    const InterpMapPoint < T, V > & other
) 
```




<hr>



### function operator== 

```C++
inline bool argos_lib::InterpMapPoint::operator== (
    const InterpMapPoint < T, V > & other
) 
```




<hr>

------------------------------
The documentation for this class was generated from the following file `C:/Users/jsime/OneDrive/Documents/Git/2025-Summer-Bot/src/argos_lib/include/argos_lib/general/interpolation.h`


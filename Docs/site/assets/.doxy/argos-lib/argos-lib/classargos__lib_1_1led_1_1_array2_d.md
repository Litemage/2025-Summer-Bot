

# Class argos\_lib::led::Array2D

**template &lt;typename T&gt;**



[**ClassList**](annotated.md) **>** [**argos\_lib**](namespaceargos__lib.md) **>** [**led**](namespaceargos__lib_1_1led.md) **>** [**Array2D**](classargos__lib_1_1led_1_1_array2_d.md)



[_**Array2D**_](classargos__lib_1_1led_1_1_array2_d.md) _representation where origin is at bottom left._

* `#include <panel.h>`





































## Public Functions

| Type | Name |
| ---: | :--- |
|   | [**Array2D**](#function-array2d-12) () = delete<br>_Disable default constructor because we need dimensions._  |
|   | [**Array2D**](#function-array2d-22) (unsigned width, unsigned height, T fillValue={}) <br>_Construct a new_ [_**Array2D**_](classargos__lib_1_1led_1_1_array2_d.md) _object._ |
|  unsigned | [**Height**](#function-height) () noexcept const<br>_Cells in vertical dimension._  |
|  unsigned | [**Width**](#function-width) () noexcept const<br>_Cells in horizontal dimension._  |
|  T & | [**at**](#function-at-12) (unsigned x, unsigned y) <br>_Get mutable reference to cell at a given coordinate._  |
|  const T & | [**at**](#function-at-22) (unsigned x, unsigned y) const<br>_Const reference to cell at a given coordinate. Useful to read a value and allowing the compiler to protect against modifications._  |




























## Public Functions Documentation




### function Array2D [1/2]

_Disable default constructor because we need dimensions._ 
```C++
argos_lib::led::Array2D::Array2D () = delete
```




<hr>



### function Array2D [2/2]

_Construct a new_ [_**Array2D**_](classargos__lib_1_1led_1_1_array2_d.md) _object._
```C++
inline argos_lib::led::Array2D::Array2D (
    unsigned width,
    unsigned height,
    T fillValue={}
) 
```





**Parameters:**


* `width` Number of cells in horizontal axis 
* `height` Number of cells in vertical axis 
* `fillValue` Initial value for all cells 




        

<hr>



### function Height 

_Cells in vertical dimension._ 
```C++
inline unsigned argos_lib::led::Array2D::Height () noexcept const
```





**Returns:**

Array height in cells 





        

<hr>



### function Width 

_Cells in horizontal dimension._ 
```C++
inline unsigned argos_lib::led::Array2D::Width () noexcept const
```





**Returns:**

Array width in cells 





        

<hr>



### function at [1/2]

_Get mutable reference to cell at a given coordinate._ 
```C++
inline T & argos_lib::led::Array2D::at (
    unsigned x,
    unsigned y
) 
```





**Note:**

This can throw an out\_of\_range exception if a cell is requested outside the bounds of the array dimensions.




**Parameters:**


* `x` Coordinate in x dimesion. 0 is leftmost cell. 
* `y` Coordinate in y dimension. 0 is bottommost cell. 



**Returns:**

Cell at specified coordinate 





        

<hr>



### function at [2/2]

_Const reference to cell at a given coordinate. Useful to read a value and allowing the compiler to protect against modifications._ 
```C++
inline const T & argos_lib::led::Array2D::at (
    unsigned x,
    unsigned y
) const
```





**Note:**

This can throw an out\_of\_range exception if a cell is requested outside the bounds of the array dimensions.




**Parameters:**


* `x` Coordinate in x dimesion. 0 is leftmost cell. 
* `y` Coordinate in y dimension. 0 is bottommost cell. 



**Returns:**

Cell at specified coordinate 





        

<hr>

------------------------------
The documentation for this class was generated from the following file `C:/Users/jsime/OneDrive/Documents/Git/2025-Summer-Bot/src/argos_lib/include/argos_lib/led/panel.h`


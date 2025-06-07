

# Class argos\_lib::HysteresisFilter

**template &lt;typename T&gt;**



[**ClassList**](annotated.md) **>** [**argos\_lib**](namespaceargos__lib.md) **>** [**HysteresisFilter**](classargos__lib_1_1_hysteresis_filter.md)



_A simple hysteresis filter for giving a bool output for a threshold._ [More...](#detailed-description)

* `#include <hysteresis_filter.h>`





































## Public Functions

| Type | Name |
| ---: | :--- |
|   | [**HysteresisFilter**](#function-hysteresisfilter-12) () = delete<br> |
|   | [**HysteresisFilter**](#function-hysteresisfilter-22) (T deactivateThreshold, T activateThreshold) <br>_Construct a new Hysteresis Filter object._  |
|  bool | [**operator()**](#function-operator()) (T newValue) <br>_Gets new status after applying hysteresis._  |




























## Detailed Description




**Template parameters:**


* `T` Type of threshold values 




    
## Public Functions Documentation




### function HysteresisFilter [1/2]

```C++
argos_lib::HysteresisFilter::HysteresisFilter () = delete
```




<hr>



### function HysteresisFilter [2/2]

_Construct a new Hysteresis Filter object._ 
```C++
inline argos_lib::HysteresisFilter::HysteresisFilter (
    T deactivateThreshold,
    T activateThreshold
) 
```





**Parameters:**


* `deactivateThreshold` Value below which output becomes false 
* `activateThreshold` Value above which output becomes true 




        

<hr>



### function operator() 

_Gets new status after applying hysteresis._ 
```C++
inline bool argos_lib::HysteresisFilter::operator() (
    T newValue
) 
```





**Parameters:**


* `newValue` Latest raw value to update the filter 



**Returns:**

Filtered value after applying newValue 





        

<hr>

------------------------------
The documentation for this class was generated from the following file `C:/Users/jsime/OneDrive/Documents/Git/2025-Summer-Bot/src/argos_lib/include/argos_lib/general/hysteresis_filter.h`


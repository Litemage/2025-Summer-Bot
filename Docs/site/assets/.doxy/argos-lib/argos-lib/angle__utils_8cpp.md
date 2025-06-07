

# File angle\_utils.cpp



[**FileList**](files.md) **>** [**argos\_lib**](dir_f9cbf5730473812e84551a5945ef39f8.md) **>** [**cpp**](dir_cf4b00708d9639a2579b4441eb30ca52.md) **>** [**general**](dir_16b6c439f6536703101f25e459a4699b.md) **>** [**angle\_utils.cpp**](angle__utils_8cpp.md)

[Go to the source code of this file](angle__utils_8cpp_source.md)



* `#include "argos_lib/general/angle_utils.h"`
* `#include <cmath>`
* `#include "units/math.h"`





































## Public Functions

| Type | Name |
| ---: | :--- |
|  units::degree\_t | [**ConstrainAngle**](#function-constrainangle) (units::degree\_t inVal, units::degree\_t minVal, units::degree\_t maxVal) <br> |
|  units::degree\_t | [**InvertedAngle**](#function-invertedangle) (units::degree\_t desiredAngle, units::degree\_t referenceAngle) <br>_Finds closest angle alias of a vector 180-degrees offset from desiredAngle relative to referencedAngle. All inputs are normalized so ranges are unbounded._  |
|  units::degree\_t | [**NearestAngle**](#function-nearestangle) (units::degree\_t desiredAngle, units::degree\_t referenceAngle) <br>_Finds closest angle alias of desiredAngle relative to referencedAngle. All inputs are normalized so ranges are unbounded._  |




























## Public Functions Documentation




### function ConstrainAngle 

```C++
units::degree_t ConstrainAngle (
    units::degree_t inVal,
    units::degree_t minVal,
    units::degree_t maxVal
) 
```





**Copyright:**

Copyright (c) Argos FRC Team 1756. Open Source Software; you can modify and/or share it under the terms of the license file in the root directory of this project. 





        

<hr>



### function InvertedAngle 

_Finds closest angle alias of a vector 180-degrees offset from desiredAngle relative to referencedAngle. All inputs are normalized so ranges are unbounded._ 
```C++
units::degree_t InvertedAngle (
    units::degree_t desiredAngle,
    units::degree_t referenceAngle
) 
```





**Parameters:**


* `desiredAngle` Angle to find 180-degree offset alias for 
* `referenceAngle` Defines desired alias range 



**Returns:**

Offset angle alias of desiredAngle in range (referencedAngle - 180\_deg, referencedAngle + 180\_deg] 





        

<hr>



### function NearestAngle 

_Finds closest angle alias of desiredAngle relative to referencedAngle. All inputs are normalized so ranges are unbounded._ 
```C++
units::degree_t NearestAngle (
    units::degree_t desiredAngle,
    units::degree_t referenceAngle
) 
```





**Parameters:**


* `desiredAngle` Angle to find alias for 
* `referenceAngle` Defines desired alias range 



**Returns:**

Angle alias of desiredAngle in range (referencedAngle - 180\_deg, referencedAngle + 180\_deg] 





        

<hr>

------------------------------
The documentation for this class was generated from the following file `C:/Users/jsime/OneDrive/Documents/Git/2025-Summer-Bot/src/argos_lib/cpp/general/angle_utils.cpp`


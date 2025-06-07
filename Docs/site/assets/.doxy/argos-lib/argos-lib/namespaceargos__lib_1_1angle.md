

# Namespace argos\_lib::angle



[**Namespace List**](namespaces.md) **>** [**argos\_lib**](namespaceargos__lib.md) **>** [**angle**](namespaceargos__lib_1_1angle.md)










































## Public Functions

| Type | Name |
| ---: | :--- |
|  units::degree\_t | [**ConstrainAngle**](#function-constrainangle) (units::degree\_t inVal, units::degree\_t minVal, units::degree\_t maxVal) <br>_Normalize angle to specified range._  |
|  double | [**ConstrainAngle**](#function-constrainangle) (double inVal, double minVal, double maxVal) <br>_Normalize angle to specified range._  |
|  units::degree\_t | [**InvertedAngle**](#function-invertedangle) (units::degree\_t desiredAngle, units::degree\_t referenceAngle) <br>_Finds closest angle alias of a vector 180-degrees offset from desiredAngle relative to referencedAngle. All inputs are normalized so ranges are unbounded._  |
|  units::degree\_t | [**NearestAngle**](#function-nearestangle) (units::degree\_t desiredAngle, units::degree\_t referenceAngle) <br>_Finds closest angle alias of desiredAngle relative to referencedAngle. All inputs are normalized so ranges are unbounded._  |




























## Public Functions Documentation




### function ConstrainAngle 

_Normalize angle to specified range._ 
```C++
units::degree_t argos_lib::angle::ConstrainAngle (
    units::degree_t inVal,
    units::degree_t minVal,
    units::degree_t maxVal
) 
```





**Parameters:**


* `inVal` Angle to constrain 
* `minVal` Normalization lower bound 
* `maxVal` Normalization upper bound 



**Returns:**

Normalized value in range [minVal, maxVal] 





        

<hr>



### function ConstrainAngle 

_Normalize angle to specified range._ 
```C++
double argos_lib::angle::ConstrainAngle (
    double inVal,
    double minVal,
    double maxVal
) 
```





**Parameters:**


* `inVal` Angle to constrain (degrees) 
* `minVal` Normalization lower bound (degrees) 
* `maxVal` Normalization upper bound (degrees) 



**Returns:**

Normalized value in range [minVal, maxVal] (degrees) 





        

<hr>



### function InvertedAngle 

_Finds closest angle alias of a vector 180-degrees offset from desiredAngle relative to referencedAngle. All inputs are normalized so ranges are unbounded._ 
```C++
units::degree_t argos_lib::angle::InvertedAngle (
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
units::degree_t argos_lib::angle::NearestAngle (
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
The documentation for this class was generated from the following file `C:/Users/jsime/OneDrive/Documents/Git/2025-Summer-Bot/src/argos_lib/include/argos_lib/general/angle_utils.h`


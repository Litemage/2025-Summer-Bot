

# Class EdgeDetector



[**ClassList**](annotated.md) **>** [**EdgeDetector**](class_edge_detector.md)



[More...](#detailed-description)


















## Public Types

| Type | Name |
| ---: | :--- |
| enum  | [**EdgeDetectSettings**](#enum-edgedetectsettings)  <br> |
| enum  | [**edgeStatus**](#enum-edgestatus)  <br> |




















## Public Functions

| Type | Name |
| ---: | :--- |
|  edgeStatus | [**Calculate**](#function-calculate) (bool curVal) <br> |
|   | [**EdgeDetector**](#function-edgedetector) (EdgeDetector::EdgeDetectSettings \_settings, bool initialValue=false) <br> |
|  std::string | [**ToString**](#function-tostring) (edgeStatus status) <br> |
|  bool | [**operator()**](#function-operator()) (bool curVal) <br> |




























## Detailed Description




**Copyright:**

Copyright (c) Argos FRC Team 1756. Open Source Software; you can modify and/or share it under the terms of the license file in the root directory of this project. 





    
## Public Types Documentation




### enum EdgeDetectSettings 

```C++
enum EdgeDetector::EdgeDetectSettings {
    DETECT_BOTH,
    DETECT_FALLING,
    DETECT_RISING
};
```




<hr>



### enum edgeStatus 

```C++
enum EdgeDetector::edgeStatus {
    FALLING,
    RISING,
    ERROR,
    NONE
};
```




<hr>
## Public Functions Documentation




### function Calculate 

```C++
edgeStatus EdgeDetector::Calculate (
    bool curVal
) 
```




<hr>



### function EdgeDetector 

```C++
explicit EdgeDetector::EdgeDetector (
    EdgeDetector::EdgeDetectSettings _settings,
    bool initialValue=false
) 
```




<hr>



### function ToString 

```C++
std::string EdgeDetector::ToString (
    edgeStatus status
) 
```




<hr>



### function operator() 

```C++
bool EdgeDetector::operator() (
    bool curVal
) 
```




<hr>

------------------------------
The documentation for this class was generated from the following file `C:/Users/jsime/OneDrive/Documents/Git/2025-Summer-Bot/src/argos_lib/include/argos_lib/general/edge_detector.h`


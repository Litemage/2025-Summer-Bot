

# Class argos\_lib::EdgeDetector



[**ClassList**](annotated.md) **>** [**argos\_lib**](namespaceargos__lib.md) **>** [**EdgeDetector**](classargos__lib_1_1_edge_detector.md)






















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




























## Public Types Documentation




### enum EdgeDetectSettings 

```C++
enum argos_lib::EdgeDetector::EdgeDetectSettings {
    DETECT_BOTH,
    DETECT_FALLING,
    DETECT_RISING
};
```




<hr>



### enum edgeStatus 

```C++
enum argos_lib::EdgeDetector::edgeStatus {
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
edgeStatus argos_lib::EdgeDetector::Calculate (
    bool curVal
) 
```




<hr>



### function EdgeDetector 

```C++
explicit argos_lib::EdgeDetector::EdgeDetector (
    EdgeDetector::EdgeDetectSettings _settings,
    bool initialValue=false
) 
```




<hr>



### function ToString 

```C++
std::string argos_lib::EdgeDetector::ToString (
    edgeStatus status
) 
```




<hr>



### function operator() 

```C++
bool argos_lib::EdgeDetector::operator() (
    bool curVal
) 
```




<hr>

------------------------------
The documentation for this class was generated from the following file `C:/Users/jsime/OneDrive/Documents/Git/2025-Summer-Bot/src/argos_lib/include/argos_lib/general/edge_detector.h`


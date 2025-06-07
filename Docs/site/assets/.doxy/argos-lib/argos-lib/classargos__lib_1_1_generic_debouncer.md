

# Class argos\_lib::GenericDebouncer

**template &lt;class T&gt;**



[**ClassList**](annotated.md) **>** [**argos\_lib**](namespaceargos__lib.md) **>** [**GenericDebouncer**](classargos__lib_1_1_generic_debouncer.md)










































## Public Functions

| Type | Name |
| ---: | :--- |
|   | [**GenericDebouncer**](#function-genericdebouncer) (const units::millisecond\_t symmetricDebounceTime, T initialValue={}) <br>_Construct a new_ [_**Debouncer**_](classargos__lib_1_1_debouncer.md) _object with symmetric times._ |
|  void | [**Reset**](#function-reset) (T newVal) <br> |
|  T | [**operator()**](#function-operator()) (T newVal) <br>_Update debouncer with new input and retreive latest debounced status._  |




























## Public Functions Documentation




### function GenericDebouncer 

_Construct a new_ [_**Debouncer**_](classargos__lib_1_1_debouncer.md) _object with symmetric times._
```C++
inline explicit argos_lib::GenericDebouncer::GenericDebouncer (
    const units::millisecond_t symmetricDebounceTime,
    T initialValue={}
) 
```





**Parameters:**


* `symmetricDebounceTime` Symmetric activate and clear time 




        

<hr>



### function Reset 

```C++
inline void argos_lib::GenericDebouncer::Reset (
    T newVal
) 
```





**Parameters:**


* `newVal` Value to set to 




        

<hr>



### function operator() 

_Update debouncer with new input and retreive latest debounced status._ 
```C++
inline T argos_lib::GenericDebouncer::operator() (
    T newVal
) 
```





**Parameters:**


* `newVal` Latest raw value 



**Returns:**

Value after applying debounce 





        

<hr>

------------------------------
The documentation for this class was generated from the following file `C:/Users/jsime/OneDrive/Documents/Git/2025-Summer-Bot/src/argos_lib/include/argos_lib/general/generic_debouncer.h`


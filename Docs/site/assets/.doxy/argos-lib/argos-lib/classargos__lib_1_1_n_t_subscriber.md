

# Class argos\_lib::NTSubscriber



[**ClassList**](annotated.md) **>** [**argos\_lib**](namespaceargos__lib.md) **>** [**NTSubscriber**](classargos__lib_1_1_n_t_subscriber.md)



_Subscribes to Network Tables entry updates and calls a specified callback to use the new value._ 

* `#include <nt_subscriber.h>`





































## Public Functions

| Type | Name |
| ---: | :--- |
|  void | [**AddMonitor**](#function-addmonitor) (const std::string & keyName, std::function&lt; void(double)&gt; onUpdateCallback, const double defaultValue=0.0, const bool forceUpdate=true) <br>_Register a new listener for the specified key and send values to callback on update._  |
|   | [**NTSubscriber**](#function-ntsubscriber) (const std::string & tableName) <br>_Construct a new_ [_**NTSubscriber**_](classargos__lib_1_1_n_t_subscriber.md) _object._ |
|   | [**~NTSubscriber**](#function-ntsubscriber) () <br> |




























## Public Functions Documentation




### function AddMonitor 

_Register a new listener for the specified key and send values to callback on update._ 
```C++
void argos_lib::NTSubscriber::AddMonitor (
    const std::string & keyName,
    std::function< void(double)> onUpdateCallback,
    const double defaultValue=0.0,
    const bool forceUpdate=true
) 
```





**Parameters:**


* `keyName` Key to listen for updates. Will be at tableName/keyName (keyName can have more slashes) 
* `onUpdateCallback` Callback to run when keyName changes 
* `defaultValue` Default value to initialize key if it doesn't exist yet 
* `forceUpdate` When true, update network tables value to default even if another value is already set 




        

<hr>



### function NTSubscriber 

_Construct a new_ [_**NTSubscriber**_](classargos__lib_1_1_n_t_subscriber.md) _object._
```C++
explicit argos_lib::NTSubscriber::NTSubscriber (
    const std::string & tableName
) 
```





**Parameters:**


* `tableName` Name of the table containing keys to watch 




        

<hr>



### function ~NTSubscriber 

```C++
argos_lib::NTSubscriber::~NTSubscriber () 
```




<hr>

------------------------------
The documentation for this class was generated from the following file `C:/Users/jsime/OneDrive/Documents/Git/2025-Summer-Bot/src/argos_lib/include/argos_lib/general/nt_subscriber.h`


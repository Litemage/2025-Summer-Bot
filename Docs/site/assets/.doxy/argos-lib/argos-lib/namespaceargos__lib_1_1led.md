

# Namespace argos\_lib::led



[**Namespace List**](namespaces.md) **>** [**argos\_lib**](namespaceargos__lib.md) **>** [**led**](namespaceargos__lib_1_1led.md)


















## Namespaces

| Type | Name |
| ---: | :--- |
| namespace | [**animation**](namespaceargos__lib_1_1led_1_1animation.md) <br> |


## Classes

| Type | Name |
| ---: | :--- |
| struct | [**Animation**](structargos__lib_1_1led_1_1_animation.md) <br>_A representation of a custom LED animation._  |
| class | [**Array2D**](classargos__lib_1_1led_1_1_array2_d.md) &lt;typename T&gt;<br>[_**Array2D**_](classargos__lib_1_1led_1_1_array2_d.md) _representation where origin is at bottom left._ |
| struct | [**PanelScanParams**](structargos__lib_1_1led_1_1_panel_scan_params.md) <br> |
| struct | [**Sprite**](structargos__lib_1_1led_1_1_sprite.md) <br>[https://en.wikipedia.org/wiki/Sprite\_(computer\_graphics)](https://en.wikipedia.org/wiki/Sprite_(computer_graphics)) __ |


## Public Types

| Type | Name |
| ---: | :--- |
| typedef std::function&lt; [**Sprite**](structargos__lib_1_1led_1_1_sprite.md)()&gt; | [**AnimatedSprite**](#typedef-animatedsprite)  <br>_Callable to get dynamic sprite._  |
| enum  | [**FirstPixelPosition**](#enum-firstpixelposition)  <br>_When representing a panel as a strip, which pixel is the first address._  |
| typedef [**Array2D**](classargos__lib_1_1led_1_1_array2_d.md)&lt; float &gt; | [**Mask**](#typedef-mask)  <br> |
| typedef [**Array2D**](classargos__lib_1_1led_1_1_array2_d.md)&lt; frc::AddressableLED::LEDData &gt; | [**Panel**](#typedef-panel)  <br>_Pixels in a panel._  |
| enum  | [**PrimaryScanDirection**](#enum-primaryscandirection)  <br>_When representing a panel as a strip, sequential addresses are in this direction. Note that the actual scan direction will alternate on every row/column in the secondary scan direction. For example, if the primary scan direction is vertical, adjacent columns will alternate between up and down._  |
| typedef std::vector&lt; frc::AddressableLED::LEDData &gt; | [**Strip**](#typedef-strip)  <br>_A strip of LEDs._  |




















## Public Functions

| Type | Name |
| ---: | :--- |
|  units::degree\_t | [**FlipHorizontal**](#function-fliphorizontal) (units::degree\_t incidentAngle) <br>_Flip an angle horizontally as though a ray bounces off a horizontal surface._  |
|  units::degree\_t | [**FlipVertical**](#function-flipvertical) (units::degree\_t inicidentAngle) <br>_Flip an angle vertically as though a ray bounces off a vertical surface._  |
|  bool | [**PointInBox**](#function-pointinbox) (float corner1X, float corner1Y, float corner2X, float corner2Y, float pointX, float pointY) <br>_Determine if a point (pointX, pointY) is within the bounds of an axis-aligned bounding box with opposite corners (corner1X, corner1Y) and (corner2X, corner2Y)_  |
|  std::optional&lt; std::pair&lt; float, float &gt; &gt; | [**SegmentIntersection**](#function-segmentintersection) (float s1x1, float s1y1, float s1x2, float s1y2, float s2x1, float s2y1, float s2x2, float s2y2) <br>_Finds the intersection point of two lines_  _[(s1x1, s1y1), (s1x2, s1y2)] and [(s2x1, s2y1), (s2x2, s2y2)]_ _if it exists. If the two lines are colinear, no intersection point is returned._ |
|  Strip | [**Serialize**](#function-serialize) (const [**Panel**](classargos__lib_1_1led_1_1_array2_d.md) & panel, const [**PanelScanParams**](structargos__lib_1_1led_1_1_panel_scan_params.md) & params) <br>_Convert a panel to a 1D vector of pixels in addressing order. This is a helper function because many panel animations are easier to design in 2D space then convert back to address order when it comes time to display._  |




























## Public Types Documentation




### typedef AnimatedSprite 

_Callable to get dynamic sprite._ 
```C++
using argos_lib::led::AnimatedSprite =  std::function<Sprite()>;
```




<hr>



### enum FirstPixelPosition 

_When representing a panel as a strip, which pixel is the first address._ 
```C++
enum argos_lib::led::FirstPixelPosition {
    TopRight,
    TopLeft,
    BottomLeft,
    BottomRight
};
```




<hr>



### typedef Mask 

```C++
using argos_lib::led::Mask =  Array2D<float>;
```



Transparency mask (alpha channel) for a panel. Range [0,1] where 0 is fully transparent and 1 is fully opaque. 


        

<hr>



### typedef Panel 

_Pixels in a panel._ 
```C++
using argos_lib::led::Panel =  Array2D<frc::AddressableLED::LEDData>;
```




<hr>



### enum PrimaryScanDirection 

_When representing a panel as a strip, sequential addresses are in this direction. Note that the actual scan direction will alternate on every row/column in the secondary scan direction. For example, if the primary scan direction is vertical, adjacent columns will alternate between up and down._ 
```C++
enum argos_lib::led::PrimaryScanDirection {
    Vertical,
    Horizontal
};
```




<hr>



### typedef Strip 

_A strip of LEDs._ 
```C++
using argos_lib::led::Strip =  std::vector<frc::AddressableLED::LEDData>;
```




<hr>
## Public Functions Documentation




### function FlipHorizontal 

_Flip an angle horizontally as though a ray bounces off a horizontal surface._ 
```C++
units::degree_t argos_lib::led::FlipHorizontal (
    units::degree_t incidentAngle
) 
```





**Parameters:**


* `incidentAngle` Angle of original motion 



**Returns:**

Reflected angle




**Copyright:**

Copyright (c) Argos FRC Team 1756. Open Source Software; you can modify and/or share it under the terms of the license file in the root directory of this project. 





        

<hr>



### function FlipVertical 

_Flip an angle vertically as though a ray bounces off a vertical surface._ 
```C++
units::degree_t argos_lib::led::FlipVertical (
    units::degree_t inicidentAngle
) 
```





**Parameters:**


* `incidentAngle` Angle of original motion 



**Returns:**

Reflected angle 





        

<hr>



### function PointInBox 

_Determine if a point (pointX, pointY) is within the bounds of an axis-aligned bounding box with opposite corners (corner1X, corner1Y) and (corner2X, corner2Y)_ 
```C++
bool argos_lib::led::PointInBox (
    float corner1X,
    float corner1Y,
    float corner2X,
    float corner2Y,
    float pointX,
    float pointY
) 
```





**Parameters:**


* `corner1X` First corner X coordinate 
* `corner1Y` First corner Y coordinate 
* `corner2X` Second corner X coordinate 
* `corner2Y` Second corner Y coordinate 
* `pointX` Test point X coordinate 
* `pointY` Test point Y coordinate 



**Returns:**

true if point is in bounding box 





        

<hr>



### function SegmentIntersection 

_Finds the intersection point of two lines_  _[(s1x1, s1y1), (s1x2, s1y2)] and [(s2x1, s2y1), (s2x2, s2y2)]_ _if it exists. If the two lines are colinear, no intersection point is returned._
```C++
std::optional< std::pair< float, float > > argos_lib::led::SegmentIntersection (
    float s1x1,
    float s1y1,
    float s1x2,
    float s1y2,
    float s2x1,
    float s2y1,
    float s2x2,
    float s2y2
) 
```





**Parameters:**


* `s1x1` First point of first segment x coordinate 
* `s1y1` First point of first segment y coordinate 
* `s1x2` Second point of first segment x coordinate 
* `s1y2` Second point of first segment y coordinate 
* `s2x1` First point of second segment x coordinate 
* `s2y1` First point of second segment y coordinate 
* `s2x2` Second point of second segment x coordinate 
* `s2y2` Second point of second segment y coordinate 



**Returns:**

(x,y) pair indicating intersection point if it exists, std::nullopt otherwise 





        

<hr>



### function Serialize 

_Convert a panel to a 1D vector of pixels in addressing order. This is a helper function because many panel animations are easier to design in 2D space then convert back to address order when it comes time to display._ 
```C++
Strip argos_lib::led::Serialize (
    const Panel & panel,
    const PanelScanParams & params
) 
```





**Parameters:**


* `panel` Panel to serialize 
* `params` Parameters describing panel addressing and orientation 



**Returns:**

A strip representation of panel with all pixels in address order




**Copyright:**

Copyright (c) Argos FRC Team 1756. Open Source Software; you can modify and/or share it under the terms of the license file in the root directory of this project. 





        

<hr>

------------------------------
The documentation for this class was generated from the following file `C:/Users/jsime/OneDrive/Documents/Git/2025-Summer-Bot/src/argos_lib/include/argos_lib/led/animiation.h`


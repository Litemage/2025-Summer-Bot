

# Namespace argos\_lib::led::animation



[**Namespace List**](namespaces.md) **>** [**argos\_lib**](namespaceargos__lib.md) **>** [**led**](namespaceargos__lib_1_1led.md) **>** [**animation**](namespaceargos__lib_1_1led_1_1animation.md)










































## Public Functions

| Type | Name |
| ---: | :--- |
|  AnimatedSprite | [**ChompingPacMan**](#function-chompingpacman) (float radius, frc::AddressableLED::LEDData color, units::degree\_t direction, units::millisecond\_t chompPeriod, bool feathered=false) <br> |
|  void | [**DrawCircle**](#function-drawcircle) ([**Panel**](classargos__lib_1_1led_1_1_array2_d.md) & dest, float radius, float x, float y, frc::AddressableLED::LEDData color, bool feathered=false) <br>_Draw a circle to the panel._  |
|  [**Sprite**](structargos__lib_1_1led_1_1_sprite.md) | [**DrawCircleSprite**](#function-drawcirclesprite) (float radius, frc::AddressableLED::LEDData color, bool feathered=false) <br>_Generate a sprite containing a circle with transparent background._  |
|  [**Sprite**](structargos__lib_1_1led_1_1_sprite.md) | [**DrawPacMan**](#function-drawpacman) (float radius, frc::AddressableLED::LEDData color, units::degree\_t direction, units::degree\_t mouthAngle, bool feathered=false) <br>_Generate PacMan sprite :D._  |
|  void | [**DrawRectangle**](#function-drawrectangle) ([**Panel**](classargos__lib_1_1led_1_1_array2_d.md) & dest, unsigned rectWidth, unsigned rectHeight, float x, float y, frc::AddressableLED::LEDData color) <br>_Draws an axis-aligned rectangle to a panel. All pixels outside the rectangle are unmodified._  |
|  AnimatedSprite | [**DyingPacMan**](#function-dyingpacman) (float radius, frc::AddressableLED::LEDData color, units::degree\_t direction, units::degree\_t initialMouthAngle, units::millisecond\_t animationTime, bool feathered=false) <br> |
|  [**Animation**](structargos__lib_1_1led_1_1_animation.md) | [**PacManPacing**](#function-pacmanpacing) (unsigned offset, unsigned width, unsigned height, bool rainbow, frc::AddressableLED::LEDData pacManColor, argos\_lib::led::PrimaryScanDirection paceDirection, units::millisecond\_t chompPeriod, units::millisecond\_t moveSpeed, [**argos\_lib::led::PanelScanParams**](structargos__lib_1_1led_1_1_panel_scan_params.md) scanParams, bool feathered=false) <br> |
|  [**Animation**](structargos__lib_1_1led_1_1_animation.md) | [**Pong**](#function-pong) (unsigned offset, unsigned width, unsigned height, unsigned ballSize, bool rainbow, frc::AddressableLED::LEDData ballColor, frc::AddressableLED::LEDData backgroundColor, units::millisecond\_t frameTime, [**argos\_lib::led::PanelScanParams**](structargos__lib_1_1led_1_1_panel_scan_params.md) scanParams) <br>[_**Animation**_](structargos__lib_1_1led_1_1_animation.md) _that kind of works like a DVD player screensaver (_[https://youtu.be/QOtuX0jL85Y](https://youtu.be/QOtuX0jL85Y) _). A ball bounces around the panel changing color._ |
|  void | [**RenderSprite**](#function-rendersprite) ([**Panel**](classargos__lib_1_1led_1_1_array2_d.md) & dest, const [**Sprite**](structargos__lib_1_1led_1_1_sprite.md) & sprite, float x, float y, float alpha=1.0) <br>_Draw a sprite centered at a point to a panel. This will align the sprite to the nearest pixel alignment on the panel._  |




























## Public Functions Documentation




### function ChompingPacMan 

```C++
AnimatedSprite argos_lib::led::animation::ChompingPacMan (
    float radius,
    frc::AddressableLED::LEDData color,
    units::degree_t direction,
    units::millisecond_t chompPeriod,
    bool feathered=false
) 
```




<hr>



### function DrawCircle 

_Draw a circle to the panel._ 
```C++
void argos_lib::led::animation::DrawCircle (
    Panel & dest,
    float radius,
    float x,
    float y,
    frc::AddressableLED::LEDData color,
    bool feathered=false
) 
```





**Parameters:**


* `dest` Panel to draw to 
* `float` radius 
* `x` Horizontal center 
* `y` Vertical center 
* `color` Fill color 
* `feathered` When true, make border pixels semi-transparent to soften edge 




        

<hr>



### function DrawCircleSprite 

_Generate a sprite containing a circle with transparent background._ 
```C++
Sprite argos_lib::led::animation::DrawCircleSprite (
    float radius,
    frc::AddressableLED::LEDData color,
    bool feathered=false
) 
```





**Parameters:**


* `radius` Radius in pixels 
* `color` Fill color 
* `feathered` When true, make border pixels semi-transparent to soften edge 



**Returns:**

[**Sprite**](structargos__lib_1_1led_1_1_sprite.md) within square canvas with edge size ceil(2\*radius) 





        

<hr>



### function DrawPacMan 

_Generate PacMan sprite :D._ 
```C++
Sprite argos_lib::led::animation::DrawPacMan (
    float radius,
    frc::AddressableLED::LEDData color,
    units::degree_t direction,
    units::degree_t mouthAngle,
    bool feathered=false
) 
```





**Parameters:**


* `radius` Radius of our fearless hero 
* `color` Why does he _have_ to be yellow? 
* `direction` Mouth direction 
* `mouthAngle` Jaw separation angle from mandible to palate 
* `feathered` When true, make border pixels semi-transparent to soften edge 



**Returns:**

PacMan 





        

<hr>



### function DrawRectangle 

_Draws an axis-aligned rectangle to a panel. All pixels outside the rectangle are unmodified._ 
```C++
void argos_lib::led::animation::DrawRectangle (
    Panel & dest,
    unsigned rectWidth,
    unsigned rectHeight,
    float x,
    float y,
    frc::AddressableLED::LEDData color
) 
```





**Parameters:**


* `dest` Panel to draw to 
* `rectWidth` Width of rectangle in pixels 
* `rectHeight` Height of rectangle in pixels 
* `x` Rectangle center x coordinate 
* `y` Rectangle center y coordinate 
* `color` Color of drawn rectangle 




        

<hr>



### function DyingPacMan 

```C++
AnimatedSprite argos_lib::led::animation::DyingPacMan (
    float radius,
    frc::AddressableLED::LEDData color,
    units::degree_t direction,
    units::degree_t initialMouthAngle,
    units::millisecond_t animationTime,
    bool feathered=false
) 
```




<hr>



### function PacManPacing 

```C++
Animation argos_lib::led::animation::PacManPacing (
    unsigned offset,
    unsigned width,
    unsigned height,
    bool rainbow,
    frc::AddressableLED::LEDData pacManColor,
    argos_lib::led::PrimaryScanDirection paceDirection,
    units::millisecond_t chompPeriod,
    units::millisecond_t moveSpeed,
    argos_lib::led::PanelScanParams scanParams,
    bool feathered=false
) 
```




<hr>



### function Pong 

[_**Animation**_](structargos__lib_1_1led_1_1_animation.md) _that kind of works like a DVD player screensaver (_[https://youtu.be/QOtuX0jL85Y](https://youtu.be/QOtuX0jL85Y) _). A ball bounces around the panel changing color._
```C++
Animation argos_lib::led::animation::Pong (
    unsigned offset,
    unsigned width,
    unsigned height,
    unsigned ballSize,
    bool rainbow,
    frc::AddressableLED::LEDData ballColor,
    frc::AddressableLED::LEDData backgroundColor,
    units::millisecond_t frameTime,
    argos_lib::led::PanelScanParams scanParams
) 
```





**Parameters:**


* `offset` Address of first LED in controlled panel 
* `width` Width of panel in pixels 
* `height` Height of panel in pixels 
* `ballSize` Width and height of ball in pixels (it's a square... a circle would basically be the same at this size and I'm lazy) 
* `rainbow` When true, ball changes to a random hue on every bounce! 
* `ballColor` Initial color of the bouncing ball 
* `backgroundColor` Background color behind the ball 
* `frameTime` Time for ball to travel one pixel distance 
* `scanParams` Parameters controlling the serialization of the internal panel to pixel addresses 



**Returns:**

[**Animation**](structargos__lib_1_1led_1_1_animation.md) to use to control a panel with this animation pattern




**Copyright:**

Copyright (c) Argos FRC Team 1756. Open Source Software; you can modify and/or share it under the terms of the license file in the root directory of this project. 





        

<hr>



### function RenderSprite 

_Draw a sprite centered at a point to a panel. This will align the sprite to the nearest pixel alignment on the panel._ 
```C++
void argos_lib::led::animation::RenderSprite (
    Panel & dest,
    const Sprite & sprite,
    float x,
    float y,
    float alpha=1.0
) 
```





**Parameters:**


* `dest` Panel to draw to 
* `sprite` [**Sprite**](structargos__lib_1_1led_1_1_sprite.md) to draw 
* `x` Horizontal center 
* `y` Vertical center 
* `alpha` Global sprite transparency where 0 is fully transparent and 1 is fully opaque 




        

<hr>

------------------------------
The documentation for this class was generated from the following file `C:/Users/jsime/OneDrive/Documents/Git/2025-Summer-Bot/src/argos_lib/include/argos_lib/led/animiation.h`


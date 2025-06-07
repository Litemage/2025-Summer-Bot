

# File animiation.h

[**File List**](files.md) **>** [**argos\_lib**](dir_f9cbf5730473812e84551a5945ef39f8.md) **>** [**include**](dir_0330651415bf66743a1cd99e3d0db0bc.md) **>** [**argos\_lib**](dir_934baf9e7d2bb4710ca41f9f25ef3ea4.md) **>** [**led**](dir_92b511606ba5c2da7e2dda655454d24f.md) **>** [**animiation.h**](animiation_8h.md)

[Go to the documentation of this file](animiation_8h.md)


```C++


#pragma once

#include <argos_lib/led/panel.h>
#include <frc/AddressableLED.h>
#include <units/angle.h>
#include <units/time.h>

#include <algorithm>
#include <functional>

namespace argos_lib {
  namespace led {
    struct Animation {
      Animation() = delete;

      Animation(std::function<Strip()> update, unsigned numLEDs, unsigned offset)
          : update{update}, numLEDs{numLEDs}, offset{offset} {};

      std::function<Strip()> update;  
      unsigned numLEDs;               
      unsigned offset;                
    };

    struct Sprite {
      Panel colors;  
      Mask alpha;    
    };

    using AnimatedSprite = std::function<Sprite()>;  

    namespace animation {
      Animation Pong(unsigned offset,
                     unsigned width,
                     unsigned height,
                     unsigned ballSize,
                     bool rainbow,
                     frc::AddressableLED::LEDData ballColor,
                     frc::AddressableLED::LEDData backgroundColor,
                     units::millisecond_t frameTime,
                     argos_lib::led::PanelScanParams scanParams);

      AnimatedSprite ChompingPacMan(float radius,
                                    frc::AddressableLED::LEDData color,
                                    units::degree_t direction,
                                    units::millisecond_t chompPeriod,
                                    bool feathered = false);
      AnimatedSprite DyingPacMan(float radius,
                                 frc::AddressableLED::LEDData color,
                                 units::degree_t direction,
                                 units::degree_t initialMouthAngle,
                                 units::millisecond_t animationTime,
                                 bool feathered = false);

      Animation PacManPacing(unsigned offset,
                             unsigned width,
                             unsigned height,
                             bool rainbow,
                             frc::AddressableLED::LEDData pacManColor,
                             argos_lib::led::PrimaryScanDirection paceDirection,
                             units::millisecond_t chompPeriod,
                             units::millisecond_t moveSpeed,
                             argos_lib::led::PanelScanParams scanParams,
                             bool feathered = false);

      void DrawRectangle(
          Panel& dest, unsigned rectWidth, unsigned rectHeight, float x, float y, frc::AddressableLED::LEDData color);

      void DrawCircle(
          Panel& dest, float radius, float x, float y, frc::AddressableLED::LEDData color, bool feathered = false);

      Sprite DrawCircleSprite(float radius, frc::AddressableLED::LEDData color, bool feathered = false);

      void RenderSprite(Panel& dest, const Sprite& sprite, float x, float y, float alpha = 1.0);

      Sprite DrawPacMan(float radius,
                        frc::AddressableLED::LEDData color,
                        units::degree_t direction,
                        units::degree_t mouthAngle,
                        bool feathered = false);
    }  // namespace animation
  }  // namespace led
}  // namespace argos_lib
```



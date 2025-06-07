

# File led\_subsystem.h

[**File List**](files.md) **>** [**argos\_lib**](dir_f9cbf5730473812e84551a5945ef39f8.md) **>** [**include**](dir_0330651415bf66743a1cd99e3d0db0bc.md) **>** [**argos\_lib**](dir_934baf9e7d2bb4710ca41f9f25ef3ea4.md) **>** [**subsystems**](dir_74a079771991058d11b5f8805d16e2a9.md) **>** [**led\_subsystem.h**](led__subsystem_8h.md)

[Go to the documentation of this file](led__subsystem_8h.md)


```C++


#pragma once

#include <argos_lib/led/animiation.h>
#include <argos_lib/led/panel.h>
#include <ctre/phoenix/led/CANdle.h>
#include <frc/AddressableLED.h>
#include <frc2/command/SubsystemBase.h>

#include <vector>

namespace argos_lib {
  struct LEDState {
    bool animated{false};                
    frc::AddressableLED::LEDData color;  

    bool operator==(const LEDState& other) const;
    bool operator!=(const LEDState& other) const;

    LEDState& operator=(const frc::AddressableLED::LEDData& other);
  };

  class LEDSubsystem : public frc2::SubsystemBase {
   private:
    // Forward declaration
    struct LEDUpdateGroup;

   public:
    explicit LEDSubsystem(unsigned numAuxLEDs);

    void Periodic() override;

    void StockAnimateAuxLEDs(ctre::phoenix::led::Animation& animation, int slot);

    void StockAnimateIntegratedLEDs(ctre::phoenix::led::Animation& animation, int slot);

    void CustomAnimateAuxLEDs(argos_lib::led::Animation animation);

    void CustomAnimateIntegratedLEDs(argos_lib::led::Animation animation);

   private:
    std::vector<LEDState> m_currentLEDs;                        
    std::vector<LEDState> m_prevLEDs;                           
    std::vector<argos_lib::led::Animation> m_customAnimations;  
    ctre::phoenix::led::CANdle m_controller;                    

    constexpr static unsigned numIntegratedLEDs = 8;  

    std::vector<LEDUpdateGroup> GetDeltaUpdate(const std::vector<LEDState>& prev, const std::vector<LEDState>& current);

    struct LEDUpdateGroup {
      LEDUpdateGroup(unsigned startIndex, unsigned numLEDs, frc::AddressableLED::LEDData color)
          : startIndex{startIndex}, numLEDs{numLEDs}, color{color} {};

      unsigned startIndex;                 
      unsigned numLEDs;                    
      frc::AddressableLED::LEDData color;  
    };
  };
}  // namespace argos_lib
```



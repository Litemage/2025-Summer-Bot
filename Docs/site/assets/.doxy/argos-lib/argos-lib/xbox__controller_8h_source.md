

# File xbox\_controller.h

[**File List**](files.md) **>** [**argos\_lib**](dir_f9cbf5730473812e84551a5945ef39f8.md) **>** [**include**](dir_0330651415bf66743a1cd99e3d0db0bc.md) **>** [**argos\_lib**](dir_934baf9e7d2bb4710ca41f9f25ef3ea4.md) **>** [**controller**](dir_1b5ab51e1de305e693feb9e8d9da64c0.md) **>** [**xbox\_controller.h**](xbox__controller_8h.md)

[Go to the documentation of this file](xbox__controller_8h.md)


```C++


#pragma once

#include <frc/GenericHID.h>
#include <frc2/command/button/Trigger.h>

#include <array>
#include <vector>

#include "argos_lib/general/debounce_settings.h"
#include "vibration.h"

namespace argos_lib {

  class XboxController : public frc::GenericHID {
   public:
    enum class JoystickHand { kLeftHand, kRightHand };

    enum class Button {
      kA = 1,
      kB = 2,
      kX = 3,
      kY = 4,
      kBumperLeft = 5,
      kBumperRight = 6,
      kBack = 7,
      kStart = 8,
      kStickLeft = 9,
      kStickRight = 10,
      kLeftTrigger = 11,   
      kRightTrigger = 12,  
      kUp = 13,            
      kRight = 14,         
      kDown = 15,          
      kLeft = 16,          
      COUNT
    };

    struct UpdateStatus {
      bool pressed = false;          
      bool released = false;         
      bool debouncePress = false;    
      bool debounceRelease = false;  
      bool rawActive = false;        
      bool debounceActive = false;   
    };

    enum class Axis { kLeftX = 0, kLeftY = 1, kLeftTrigger = 2, kRightTrigger = 3, kRightX = 4, kRightY = 5, COUNT };

    XboxController() = delete;
    explicit XboxController(int port);

    void SetButtonDebounce(Button targetButton, DebounceSettings newSettings);

    void SwapSettings(XboxController& other);

    [[nodiscard]] double GetX(JoystickHand hand) const;
    [[nodiscard]] double GetY(JoystickHand hand) const;
    [[nodiscard]] double GetTriggerAxis(JoystickHand hand) const;

    [[nodiscard]] bool GetDebouncedButton(Button buttonIdx);
    [[nodiscard]] bool GetDebouncedButtonPressed(Button buttonIdx);
    [[nodiscard]] bool GetDebouncedButtonReleased(Button buttonIdx);

    [[nodiscard]] bool GetDebouncedButton(std::vector<Button> buttonCombo);
    [[nodiscard]] bool GetDebouncedButtonPressed(std::vector<Button> buttonCombo);
    [[nodiscard]] bool GetDebouncedButtonReleased(std::vector<Button> buttonCombo);

    [[nodiscard]] bool GetRawButton(Button buttonIdx);
    [[nodiscard]] bool GetRawButtonPressed(Button buttonIdx);
    [[nodiscard]] bool GetRawButtonReleased(Button buttonIdx);

    [[nodiscard]] bool GetRawButton(std::vector<Button> buttonCombo);
    [[nodiscard]] bool GetRawButtonPressed(std::vector<Button> buttonCombo);
    [[nodiscard]] bool GetRawButtonReleased(std::vector<Button> buttonCombo);

    VibrationModel GetVibration() const;

    void SetVibration(VibrationModel newVibrationModel);

    void UpdateVibration();

    UpdateStatus UpdateButton(Button buttonIdx);

    [[nodiscard]] frc2::Trigger TriggerRaw(Button button);

    [[nodiscard]] frc2::Trigger TriggerRaw(std::vector<Button> buttonCombo);

    [[nodiscard]] frc2::Trigger TriggerRawAnyOf(std::vector<Button> buttonCombo);

    [[nodiscard]] frc2::Trigger TriggerRawAllOf(std::vector<Button> buttonCombo);

    [[nodiscard]] frc2::Trigger TriggerRawNoneOf(std::vector<Button> buttonCombo);

    [[nodiscard]] frc2::Trigger TriggerRawOneOf(std::vector<Button> buttonCombo);

    [[nodiscard]] frc2::Trigger TriggerDebounced(Button button);

    [[nodiscard]] frc2::Trigger TriggerDebounced(std::vector<Button> buttonCombo);

    [[nodiscard]] frc2::Trigger TriggerDebouncedAnyOf(std::vector<Button> buttonCombo);

    [[nodiscard]] frc2::Trigger TriggerDebouncedAllOf(std::vector<Button> buttonCombo);

    [[nodiscard]] frc2::Trigger TriggerDebouncedNoneOf(std::vector<Button> buttonCombo);

    [[nodiscard]] frc2::Trigger TriggerDebouncedOneOf(std::vector<Button> buttonCombo);

   private:
    struct DPadButtons {
      bool up = false;     
      bool right = false;  
      bool down = false;   
      bool left = false;   
    };

    DPadButtons GetPOVButtons();

    [[nodiscard]] frc2::Trigger TriggerAnyOf(std::vector<Button> buttonCombo,
                                             std::function<bool(Button)> buttonGetterFunc);

    [[nodiscard]] frc2::Trigger TriggerAllOf(std::vector<Button> buttonCombo,
                                             std::function<bool(Button)> buttonGetterFunc);

    [[nodiscard]] frc2::Trigger TriggerNoneOf(std::vector<Button> buttonCombo,
                                              std::function<bool(Button)> buttonGetterFunc);

    [[nodiscard]] frc2::Trigger TriggerOneOf(std::vector<Button> buttonCombo,
                                             std::function<bool(Button)> buttonGetterFunc);

    constexpr static double analogTriggerThresh = 0.5;  

    std::array<DebounceSettings, static_cast<int>(Button::COUNT)> m_buttonDebounceSettings;
    std::array<bool, static_cast<int>(Button::COUNT)> m_buttonDebounceStatus;
    std::array<bool, static_cast<int>(Button::COUNT)> m_rawButtonStatus;
    std::array<std::chrono::time_point<std::chrono::steady_clock>, static_cast<int>(Button::COUNT)>
        m_buttonDebounceTransitionTime;  

    VibrationModel m_vibrationModel;  
  };

}  // namespace argos_lib
```



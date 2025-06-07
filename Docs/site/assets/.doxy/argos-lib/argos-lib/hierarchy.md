
# Class Hierarchy

This inheritance list is sorted roughly, but not completely, alphabetically:


* **class** [**Debouncer**](class_debouncer.md) 
* **class** [**EdgeDetector**](class_edge_detector.md) 
* **class** [**NTMotorPIDTuner**](class_n_t_motor_p_i_d_tuner.md) _Allows user to set PID parameters from network tables and update the motor configurations on updates. Also monitors status information from motors to aid tuning._ 
* **class** [**NTSubscriber**](class_n_t_subscriber.md) _Subscribes to Network Tables entry updates and calls a specified callback to use the new value._ 
* **class** [**argos\_lib::SwerveHomeStorageInterface**](classargos__lib_1_1_swerve_home_storage_interface.md) _Interface capable of saving and loading module home positions from persistent storage._     
    * **class** [**argos\_lib::SwerveFSHomingStorage**](classargos__lib_1_1_swerve_f_s_homing_storage.md) 
    * **class** [**argos\_lib::swerve::NetworkTablesHomingStorage**](classargos__lib_1_1swerve_1_1_network_tables_homing_storage.md) _Saves and loads swerve module homes to networkTables._ 
* **class** [**argos\_lib::ArgosLogger**](classargos__lib_1_1_argos_logger.md) _Log to the console in a clean, repeatable manner._ 
* **class** [**argos\_lib::Debouncer**](classargos__lib_1_1_debouncer.md) 
* **class** [**argos\_lib::EdgeDetector**](classargos__lib_1_1_edge_detector.md) 
* **class** [**argos\_lib::HomingStorageInterface**](classargos__lib_1_1_homing_storage_interface.md) _Interface capable of saving and loading home positions from persistent storage._     
    * **class** [**argos\_lib::FSHomingStorage**](classargos__lib_1_1_f_s_homing_storage.md) _Saves and loads home positions from filesystem._ 
* **class** [**argos\_lib::GenericDebouncer**](classargos__lib_1_1_generic_debouncer.md) 
* **class** [**argos\_lib::HysteresisFilter**](classargos__lib_1_1_hysteresis_filter.md) _A simple hysteresis filter for giving a bool output for a threshold._ 
* **class** [**argos\_lib::InterpolationMap**](classargos__lib_1_1_interpolation_map.md) _Performs linear interpolation of a value based on a set of input-&gt;output mapping points._ 
* **class** [**argos\_lib::NTMotorPIDTuner**](classargos__lib_1_1_n_t_motor_p_i_d_tuner.md) _Allows user to set PID parameters from network tables and update the motor configurations on updates. Also monitors status information from motors to aid tuning._ 
* **class** [**argos\_lib::NTSubscriber**](classargos__lib_1_1_n_t_subscriber.md) _Subscribes to Network Tables entry updates and calls a specified callback to use the new value._ 
* **class** [**argos\_lib::led::Array2D**](classargos__lib_1_1led_1_1_array2_d.md) [_**Array2D**_](classargos__lib_1_1led_1_1_array2_d.md) _representation where origin is at bottom left._
* **struct** [**ClosedLoopSensorConversions**](struct_closed_loop_sensor_conversions.md) _Conversion factors to aid displaying sensor values as meaningful numbers._ 
* **struct** [**argos\_lib::ArgosColor**](structargos__lib_1_1_argos_color.md) 
* **struct** [**argos\_lib::CANAddress**](structargos__lib_1_1_c_a_n_address.md) 
* **struct** [**argos\_lib::ClosedLoopSensorConversions**](structargos__lib_1_1_closed_loop_sensor_conversions.md) _Conversion factors to aid displaying sensor values as meaningful numbers._ 
* **struct** [**argos\_lib::DebounceSettings**](structargos__lib_1_1_debounce_settings.md) 
* **struct** [**argos\_lib::InterpMapPoint**](structargos__lib_1_1_interp_map_point.md) _Point that helps generate an interpolation map._ 
* **struct** [**argos\_lib::LEDState**](structargos__lib_1_1_l_e_d_state.md) _Color and animation status for an individual LED._ 
* **struct** [**argos\_lib::VibrationStatus**](structargos__lib_1_1_vibration_status.md) _Vibration percentages that can be sent to controller for user feedback._ 
* **struct** [**argos\_lib::XboxController::UpdateStatus**](structargos__lib_1_1_xbox_controller_1_1_update_status.md) _State of an individual button._ 
* **struct** [**argos\_lib::led::Animation**](structargos__lib_1_1led_1_1_animation.md) _A representation of a custom LED animation._ 
* **struct** [**argos\_lib::led::PanelScanParams**](structargos__lib_1_1led_1_1_panel_scan_params.md) 
* **struct** [**argos\_lib::led::Sprite**](structargos__lib_1_1led_1_1_sprite.md) [https://en.wikipedia.org/wiki/Sprite\_(computer\_graphics)](https://en.wikipedia.org/wiki/Sprite_(computer_graphics)) __
* **struct** [**argos\_lib::swerve::SwerveModulePositions**](structargos__lib_1_1swerve_1_1_swerve_module_positions.md) _Representation of the absolute encoder position of each module at home position._ 
* **struct** [**argos\_lib::swerve::TranslationSpeeds**](structargos__lib_1_1swerve_1_1_translation_speeds.md) _Translation speeds as percent max output._ 
* **struct** [**argos\_lib::LEDSubsystem::LEDUpdateGroup**](structargos__lib_1_1_l_e_d_subsystem_1_1_l_e_d_update_group.md) _Represents a contiguous block of LEDs that have the same color._ 
* **struct** [**argos\_lib::XboxController::DPadButtons**](structargos__lib_1_1_xbox_controller_1_1_d_pad_buttons.md) _Parsed directional pad button states._ 
* **class** **frc2::SubsystemBase**    
    * **class** [**argos\_lib::LEDSubsystem**](classargos__lib_1_1_l_e_d_subsystem.md) 
    * **class** [**argos\_lib::SwappableControllersSubsystem**](classargos__lib_1_1_swappable_controllers_subsystem.md) _Allows two controllers to swap between "Driver" and "Operator" control schemes on the fly by swapping the m\_driverController and m\_operatorController objects._ 
* **class** **frc2::CommandHelper< frc2::Command, SwapControllersCommand >**    
    * **class** [**argos\_lib::SwapControllersCommand**](classargos__lib_1_1_swap_controllers_command.md) _Swaps rolls of two controllers. Useful if one controller breaks during a match._ 
* **class** **frc::GenericHID**    
    * **class** [**argos\_lib::XboxController**](classargos__lib_1_1_xbox_controller.md) 


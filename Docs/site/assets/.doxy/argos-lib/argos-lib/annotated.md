
# Class List


Here are the classes, structs, unions and interfaces with brief descriptions:

* **struct** [**ClosedLoopSensorConversions**](struct_closed_loop_sensor_conversions.md) _Conversion factors to aid displaying sensor values as meaningful numbers._     
* **class** [**Debouncer**](class_debouncer.md)     
* **class** [**EdgeDetector**](class_edge_detector.md)     
* **class** [**NTMotorPIDTuner**](class_n_t_motor_p_i_d_tuner.md) _Allows user to set PID parameters from network tables and update the motor configurations on updates. Also monitors status information from motors to aid tuning._     
* **class** [**NTSubscriber**](class_n_t_subscriber.md) _Subscribes to Network Tables entry updates and calls a specified callback to use the new value._     
* **class** [**NetworkTablesHomingStorage**](class_network_tables_homing_storage.md) _Saves and loads swerve module homes to networkTables._     
* **class** [**SwerveFSHomingStorage**](class_swerve_f_s_homing_storage.md)     
* **namespace** [**anonymous namespace{C:/Users/jsime/OneDrive/Documents/Git/2025-Summer-Bot/src/argos\_lib/cpp/controller/trigger\_composition.cpp}**](namespace_0d021340233307002300012131121075213041020030267162.md) 
* **namespace** [**argos\_lib**](namespaceargos__lib.md)     
    * **struct** [**ArgosColor**](structargos__lib_1_1_argos_color.md)     
    * **class** [**ArgosLogger**](classargos__lib_1_1_argos_logger.md) _Log to the console in a clean, repeatable manner._     
    * **struct** [**CANAddress**](structargos__lib_1_1_c_a_n_address.md)     
    * **struct** [**ClosedLoopSensorConversions**](structargos__lib_1_1_closed_loop_sensor_conversions.md) _Conversion factors to aid displaying sensor values as meaningful numbers._     
    * **struct** [**DebounceSettings**](structargos__lib_1_1_debounce_settings.md)     
    * **class** [**Debouncer**](classargos__lib_1_1_debouncer.md)     
    * **class** [**EdgeDetector**](classargos__lib_1_1_edge_detector.md)     
    * **class** [**FSHomingStorage**](classargos__lib_1_1_f_s_homing_storage.md) _Saves and loads home positions from filesystem._     
    * **class** [**GenericDebouncer**](classargos__lib_1_1_generic_debouncer.md)     
    * **class** [**HomingStorageInterface**](classargos__lib_1_1_homing_storage_interface.md) _Interface capable of saving and loading home positions from persistent storage._     
    * **class** [**HysteresisFilter**](classargos__lib_1_1_hysteresis_filter.md) _A simple hysteresis filter for giving a bool output for a threshold._     
    * **struct** [**InterpMapPoint**](structargos__lib_1_1_interp_map_point.md) _Point that helps generate an interpolation map._     
    * **class** [**InterpolationMap**](classargos__lib_1_1_interpolation_map.md) _Performs linear interpolation of a value based on a set of input-&gt;output mapping points._     
    * **struct** [**LEDState**](structargos__lib_1_1_l_e_d_state.md) _Color and animation status for an individual LED._     
    * **class** [**LEDSubsystem**](classargos__lib_1_1_l_e_d_subsystem.md)     
    * **class** [**NTMotorPIDTuner**](classargos__lib_1_1_n_t_motor_p_i_d_tuner.md) _Allows user to set PID parameters from network tables and update the motor configurations on updates. Also monitors status information from motors to aid tuning._     
    * **class** [**NTSubscriber**](classargos__lib_1_1_n_t_subscriber.md) _Subscribes to Network Tables entry updates and calls a specified callback to use the new value._     
    * **class** [**SwapControllersCommand**](classargos__lib_1_1_swap_controllers_command.md) _Swaps rolls of two controllers. Useful if one controller breaks during a match._     
    * **class** [**SwappableControllersSubsystem**](classargos__lib_1_1_swappable_controllers_subsystem.md) _Allows two controllers to swap between "Driver" and "Operator" control schemes on the fly by swapping the m\_driverController and m\_operatorController objects._     
    * **class** [**SwerveFSHomingStorage**](classargos__lib_1_1_swerve_f_s_homing_storage.md)     
    * **class** [**SwerveHomeStorageInterface**](classargos__lib_1_1_swerve_home_storage_interface.md) _Interface capable of saving and loading module home positions from persistent storage._     
    * **struct** [**VibrationStatus**](structargos__lib_1_1_vibration_status.md) _Vibration percentages that can be sent to controller for user feedback._     
    * **class** [**XboxController**](classargos__lib_1_1_xbox_controller.md)     
        * **struct** [**UpdateStatus**](structargos__lib_1_1_xbox_controller_1_1_update_status.md) _State of an individual button._     
    * **namespace** [**angle**](namespaceargos__lib_1_1angle.md)     
    * **namespace** [**cancoder\_config**](namespaceargos__lib_1_1cancoder__config.md)     
    * **namespace** [**colors**](namespaceargos__lib_1_1colors.md)     
    * **namespace** [**falcon\_config**](namespaceargos__lib_1_1falcon__config.md)     
    * **namespace** [**gamma\_corrected\_colors**](namespaceargos__lib_1_1gamma__corrected__colors.md)     
    * **namespace** [**led**](namespaceargos__lib_1_1led.md)     
        * **struct** [**Animation**](structargos__lib_1_1led_1_1_animation.md) _A representation of a custom LED animation._     
        * **class** [**Array2D**](classargos__lib_1_1led_1_1_array2_d.md) [_**Array2D**_](classargos__lib_1_1led_1_1_array2_d.md) _representation where origin is at bottom left._    
        * **struct** [**PanelScanParams**](structargos__lib_1_1led_1_1_panel_scan_params.md)     
        * **struct** [**Sprite**](structargos__lib_1_1led_1_1_sprite.md) [https://en.wikipedia.org/wiki/Sprite\_(computer\_graphics)](https://en.wikipedia.org/wiki/Sprite_(computer_graphics)) __    
        * **namespace** [**animation**](namespaceargos__lib_1_1led_1_1animation.md)     
    * **namespace** [**odometry\_aim**](namespaceargos__lib_1_1odometry__aim.md)     
    * **namespace** [**status\_frame\_config**](namespaceargos__lib_1_1status__frame__config.md)     
    * **namespace** [**swerve**](namespaceargos__lib_1_1swerve.md)     
        * **class** [**NetworkTablesHomingStorage**](classargos__lib_1_1swerve_1_1_network_tables_homing_storage.md) _Saves and loads swerve module homes to networkTables._     
        * **struct** [**SwerveModulePositions**](structargos__lib_1_1swerve_1_1_swerve_module_positions.md) _Representation of the absolute encoder position of each module at home position._     
        * **struct** [**TranslationSpeeds**](structargos__lib_1_1swerve_1_1_translation_speeds.md) _Translation speeds as percent max output._     
    * **namespace** [**talonsrx\_config**](namespaceargos__lib_1_1talonsrx__config.md)     
    * **namespace** [**testing**](namespaceargos__lib_1_1testing.md)     
    * **namespace** [**triggers**](namespaceargos__lib_1_1triggers.md)     
* **struct** [**LEDUpdateGroup**](structargos__lib_1_1_l_e_d_subsystem_1_1_l_e_d_update_group.md) _Represents a contiguous block of LEDs that have the same color._     
* **struct** [**DPadButtons**](structargos__lib_1_1_xbox_controller_1_1_d_pad_buttons.md) _Parsed directional pad button states._     
* **namespace** [**frc**](namespacefrc.md) 
* **namespace** [**frc2**](namespacefrc2.md) 
* **namespace** [**chrono\_literals**](namespacestd_1_1literals_1_1chrono__literals.md) 


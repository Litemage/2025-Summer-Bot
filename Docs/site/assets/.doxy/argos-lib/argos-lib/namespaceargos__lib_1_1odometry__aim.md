

# Namespace argos\_lib::odometry\_aim



[**Namespace List**](namespaces.md) **>** [**argos\_lib**](namespaceargos__lib.md) **>** [**odometry\_aim**](namespaceargos__lib_1_1odometry__aim.md)










































## Public Functions

| Type | Name |
| ---: | :--- |
|  units::degree\_t | [**GetAngleToTarget**](#function-getangletotarget) (const frc::Translation2d & currentEstimatedRobotPose, const frc::Translation3d & targetPoseOnField) <br>_Gets the Angle(Yaw) required for the Robot to orient towards the target of interest assuming the robot is field-centric._  |
|  units::meter\_t | [**GetDistanceToTarget**](#function-getdistancetotarget) (const frc::Translation2d & currentEstimatedRobotPose, const frc::Translation3d & targetPoseOnField) <br>_Gets the Distance of the Robot to from the target of interest._  |




























## Public Functions Documentation




### function GetAngleToTarget 

_Gets the Angle(Yaw) required for the Robot to orient towards the target of interest assuming the robot is field-centric._ 
```C++
units::degree_t argos_lib::odometry_aim::GetAngleToTarget (
    const frc::Translation2d & currentEstimatedRobotPose,
    const frc::Translation3d & targetPoseOnField
) 
```





**Parameters:**


* `currentEstimatedRobotPose` Fused pose of the robot currently on the field 
* `targetPoseOnField` Defines desired alias range 



**Returns:**

Angle(Yaw) of robot in degrees




**Copyright:**

Copyright (c) Argos FRC Team 1756. Open Source Software; you can modify and/or share it under the terms of the license file in the root directory of this project. 





        

<hr>



### function GetDistanceToTarget 

_Gets the Distance of the Robot to from the target of interest._ 
```C++
units::meter_t argos_lib::odometry_aim::GetDistanceToTarget (
    const frc::Translation2d & currentEstimatedRobotPose,
    const frc::Translation3d & targetPoseOnField
) 
```





**Parameters:**


* `currentEstimatedRobotPose` Fused pose of the robot currently on the field 
* `targetPoseOnField` Defines desired alias range 



**Returns:**

Distance in inches of robot from the target of interest 





        

<hr>

------------------------------
The documentation for this class was generated from the following file `C:/Users/jsime/OneDrive/Documents/Git/2025-Summer-Bot/src/argos_lib/include/argos_lib/general/odometry_aim.h`


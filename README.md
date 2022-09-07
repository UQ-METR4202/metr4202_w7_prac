# metr4202_w7_prac

In this practical the `dynamixel_interface` ROS package is introduced to students to allow for control of the joint angles for each Dynamixel motor. The package was originally developed by `csiro-robotics` which has been forked under `UQ-METR4202` to pre-configure the Dynamixel controllers such that it should work for the course robots out of the box. Follow the steps under `Dynamixel Setup` in the course's resources repository, `RPi4_Setup.md`, to begin utilising the `dynamixel_interface` package.

## Usage

Once the packages are cloned, built and sourced, the `dynamixel_interface_controller_node` can be launched alongside a slider GUI for your convenience. The commands to run are the following.

```SH
# Only the Dynamixel controller
roslaunch dynamixel_interface dynamixel_interface_controller.launch
```

```SH
# Both controller and slider
roslaunch dynamixel_interface dynamixel_interface_slider.launch
```

*Be mindful both should not run simultaneously.*

The idea behind using the ROS package is that it allows for your team to publish joint commands to the `dynamixel_interface_controller_node` which subscribes to the topic `/desired_joint_states` to communicate with the motors via the USB serial port. In return a `/joint_states` topic is published by the controller node as feedback of the current state of your robot. Both topics use the `sensor_msgs/JointState` message so it is recommended to become familiar with the fields in this type.

When developing your ROS stack, you will need to launch only the `dynamixel_interface_controller_node` and not including the slider. The slider is purely for debugging and visualisation.

## This package

This repository is itself a ROS package which students can clone into their `catkin_ws/src` directly and build.
** FURTHER DETAILS TO BE RELEASE SOON! **

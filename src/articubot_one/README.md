# Project

## Overview

This project is set up to run on Ubuntu with ROS 2 Iron. It involves the installation of several ROS 2 packages and dependencies required for development and simulation tasks.

## Requirements

- **Operating System**: Ubuntu
- **ROS Version**: ROS 2 Iron

## Installation Instructions

To get started with this project, you need to install the necessary ROS 2 packages. Follow the steps below to set up your environment:

1. **Update your package lists**:
   ```bash
   sudo apt update
   ```

2. **Install required ROS 2 packages**:
   ```bash
   sudo apt install ros-iron-xacro ros-iron-joint-state-publisher-gui
   sudo apt install ros-iron-gazebo-ros-pkgs
   sudo apt-get install ros-iron-ros-gz
   sudo apt install ros-iron-rplidar-ros
   sudo apt install v4l-utils ros-iron-v4l2-camera ros-iron-image-transport-plugins
   sudo apt install ros-iron-ros2-control ros-iron-ros2-controllers ros-iron-gazebo-ros2-control
   sudo apt-get install ros-iron-twist-mux
   ```

3. **Configure your Joystick**:
Choose the enable buttons in ```src/articubot_one/config/joystick.yaml```


4. **Build the package**:
   ```bash
   colcon build --symlink-install
   ```

## Running instructions

1. **Running the simulation in Gazebo**:
   ```bash
   ros2 launch articubot_one launch_sim.launch.py world:=src/articubot_one/worlds/obstacles.world
   ```

2. **Running RVIZ**:
   ```bash
   ros2 run rviz2 rviz2 -d src/articubot_one/config/map.rviz --ros-args -p use_sim_time:=true
   ```

## Additional Information

- **xacro**: XML macro package for ROS, used to simplify the creation of URDF files.
- **joint-state-publisher-gui**: Provides a graphical interface for controlling joint states.
- **gazebo-ros-pkgs**: Integration between ROS and Gazebo for simulation purposes.
- **ros-gz**: Package for ROS-Gazebo bridge.
- **rplidar-ros**: ROS driver for RPLIDAR devices.
- **v4l-utils**: Utilities for Video4Linux, useful for camera handling.
- **v4l2-camera**: ROS 2 package for Video4Linux2 cameras.
- **image-transport-plugins**: Plugins for image transport in ROS 2.
- **ros2-control**: Control framework for ROS 2.
- **ros2-controllers**: Controllers for the ROS 2 control framework.
- **gazebo-ros2-control**: Integration between ROS 2 control and Gazebo for simulation.
- **twist-mux**: ROS 2 package for multiplexing velocity commands.

## Troubleshooting

If you encounter issues during installation or setup, ensure that your package lists are updated and that you are using the correct version of ROS. Refer to the ROS 2 documentation or community forums for additional support.

## License

Specify the license under which this project is distributed, if applicable.

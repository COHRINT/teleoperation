# COHRINT Teleop

This repo makes use of the modified teleoperation package provided by [Clearpath Robotics](https://www.clearpathrobotics.com/assets/guides/melodic/jackal/simulation.html).

Requriers a working installation of ROS Noetic, and the teleop-twist-joy package which can be installed via `sudo apt install ros-noetic-teleop-twist-joy`.

### Launching the teleop node

First, clone this github repo, and navigate into `teleoperation/robot_control` and run the following commands:

```
catkin_make
source devel/setup.sh
```

Then, to launch the teleop node, run the following command:

```
roslaunch robot_control teleop.launch joy_dev:=/dev/input/js0 robot_name:=ROBOT_NAME
```

Teleop topics should be then remapped from their default `bluetooth_teleop` topics to `ROBOT_NAME/bluetooth_teleop`

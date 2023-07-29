# COHRINT Teleop for Jackal

This repo makes use of the modified teleoperation package provided by [Clearpath Robotics](https://www.clearpathrobotics.com/assets/guides/melodic/jackal/simulation.html).

Requriers a working installation of ROS Melodic.

### Launching the teleop node

First, clone this github repo, and run the following command:

```
roslaunch jackal_control teleop.launch joy_dev:=/dev/input/js0 robot_name:=ROBOT_NAME
```

Teleop topics should be then remapped from their default `bluetooth_teleop` topics to `ROBOT_NAME/bluetooth_teleop`

### For use in the sim

If you intend to run teleop nodes in the jackal simulator, the files altered belong to the following file directories.

```
control.launch

└── jackal
    ├── jackal_control
    │   ├── CHANGELOG.rst
    │   ├── CMakeLists.txt
    │   ├── config
    │   │   ├── control.yaml
    │   │   ├── robot_localization_gx5.yaml
    │   │   ├── robot_localization.yaml
    │   │   ├── teleop_ps3.yaml
    │   │   ├── teleop_ps4.yaml
    │   │   └── twist_mux.yaml
    │   ├── launch
    │   │   ├── control.launch
    │   │   └── teleop.launch
    │   ├── package.xml
    │   └── README.md

jackal_world.launch and spawn_jackal.launch

└── jackal_simulator
    ├── jackal_gazebo
    │   ├── CHANGELOG.rst
    │   ├── CMakeLists.txt
    │   ├── launch
    │   │   ├── empty_world.launch
    │   │   ├── hrtac_world.launch
    │   │   ├── jackal_world.launch
    │   │   └── spawn_jackal.launch
    │   ├── Media
    │   │   └── models
    │   │       ├── OliveTree1.dae
    │   │       ├── OliveTree2.dae
    │   │       ├── PineTree.dae
    │   │       ├── scenario1.dae
    │   │       └── textures
    │   │           ├── mtt.png
    │   │           ├── texture0.jpg
    │   │           ├── texture0.png
    │   │           └── Vegetation_Grass1.jpg
    │   ├── package.xml
    │   └── worlds
    │       ├── jackal_race.world
    │       └── scenario1.world
    ├── jackal_simulator
    │   ├── CHANGELOG.rst
    │   ├── CMakeLists.txt
    │   └── package.xml
    └── LICENSE

```

To then run the sim, excecute the following command:

```
roslaunch jackal_gazebo jackal_world.launch robot_name:=ROBOT_NAME
```

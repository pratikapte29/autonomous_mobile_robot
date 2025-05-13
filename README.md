# Autonomous Mobile Robot (ROS 2)

This repository contains the simulation and navigation stack for an autonomous mobile robot using ROS 2. It enables teleoperation, SLAM (Simultaneous Localization and Mapping), and autonomous navigation using the Nav2 stack. The system is simulated in Gazebo, visualized in Rviz2, and supports map saving and reuse for autonomous path planning.

---

## How to Run

Follow these steps to bring up the simulation, build a map, save it, and then use it for navigation:

---

### 1. Launch the simulation environment

```bash
ros2 launch mobile_robot launch_sim.launch.py
```

---

### 2. Open R-Viz for visualization

```bash
rviz2
```

### 3. Start SLAM to begin mapping

```bash
ros2 launch slam_toolbox online_async_launch.py slam_params_file:=./src/mobile_robot/config/mapper_params_online_async.yaml use_sim_time:=true
```

### 4. Teleoperate the robot to explore and build the map

```bash
ros2 run teleop_twist_keyboard teleop_twist_keyboard
```

### 5. Save the map

```bash
ros2 run nav2_map_server map_server --ros-args -p yaml_filename:=room_map_save.yaml -p use_sim_time:=true
```

### 6. Load the Map Server

```bash
ros2 run nav2_util lifecycle_bringup map_server
```

### 7. Launch the Navigation

```bash
ros2 launch nav2_bringup navigation_launch.py use_sim_time:=true
```

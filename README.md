# Autonomous Mobile Robot (ROS 2)

This repository contains the simulation and navigation stack for an autonomous mobile robot using ROS 2. It enables teleoperation, SLAM (Simultaneous Localization and Mapping), and autonomous navigation using the Nav2 stack. The system is simulated in Gazebo, visualized in Rviz2, and supports map saving and reuse for autonomous path planning.

---

## 📦 Features

- Teleoperation via keyboard
- Real-time SLAM using `slam_toolbox`
- Autonomous navigation with `nav2_bringup`
- Visualization using Rviz2
- Map saving and reuse
- Fully simulated environment

---

## 🔧 How to Run

Follow these steps to bring up the simulation, build a map, save it, and then use it for navigation:

---

### 1. Launch the simulation environment

```bash
ros2 launch mobile_robot launch_sim.launch.py

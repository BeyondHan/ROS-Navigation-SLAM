# ROS Navigation & Path Planning Demo 🚀

**Author:** Chaoyue Han (BeyondHan)  
**GitHub:** [https://github.com/BeyondHan](https://github.com/BeyondHan)  

Welcome to the ROS Navigation & Path Planning demonstration repository! This project provides a complete, easy-to-run environment for ROS (Robot Operating System) navigation, mapping (SLAM), and path planning. It strictly adheres to standard ROS structures and is fully tested on ROS Noetic.

## 🎯 Project Overview

This repository integrates URDF modeling, Gazebo physics simulation, and the ROS Navigation Stack (`move_base`, `amcl`, `gmapping`, `map_server`). It contains three main ROS packages:

1.  **`urdf01_rviz`**: Basic static URDF modeling and visualization in RViz.
2.  **`urdf02_gazebo`**: Gazebo simulation with complete sensors (Laser, RGB Camera, Kinect Depth Camera) and differential drive plugins.
3.  **`nav_demo`**: Core navigation logic. Contains SLAM (gmapping), map saving, AMCL localization, and `move_base` DWA path planning configs.

## 🛠️ Features

*   **Virtual Robot Sandbox**: Custom car model in an enclosed Gazebo world.
*   **Sensor Fusion**: Simulated 2D LiDAR (`/scan`) and Odometry (`/odom`).
*   **Adaptive Monte Carlo Localization (AMCL)**: Integrated probabilistic localization in a pre-built static map.
*   **Autonomous Path Planning**: Global planner and Local planner (DWA) configured with custom Costmaps (inflation zones, obstacle tracking).

## 🚀 Getting Started

### 1. Prerequisites & Dependencies
Ensure you have ROS Noetic installed along with navigation and gazebo controllers:
```bash
sudo apt-get install ros-noetic-gazebo-ros-pkgs ros-noetic-gazebo-ros-control 
sudo apt-get install ros-noetic-gmapping ros-noetic-map-server ros-noetic-navigation
```

### 2. Build the Workspace
Clone this repository into your `src` folder of your catkin workspace (e.g., `~/catkin_ws/src`), then build:
```bash
cd ~/catkin_ws
catkin_make
source devel/setup.bash
```

### 3. Running Path Planning (One-Click)

**Step 1:** Launch the Gazebo simulation environment
```bash
roslaunch urdf02_gazebo env.launch
```

**Step 2:** Launch Navigation (Map + AMCL + Move Base + RViz)
```bash
roslaunch nav_demo test_path.launch
```

**Step 3:** Set a Goal
In the RViz interface, use the **`2D Nav Goal`** tool at the top toolbar and click a target destination on the map. The autonomous car will plan a path, avoid obstacles, and navigate towards the goal!

---
*If this project helps you in your research, robotics journey, or coursework, feel free to give it a ⭐!*

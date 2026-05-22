---
layout: post

# ── TITLE & DESCRIPTION ──────────────────────────────────────────────────────
title: Vision-Guided Pick & Place with ROS2 and MoveIt 2   # h1 shown at the top of the page
description: Developed a full ROS2 Humble pipeline for autonomous pick and place on a Kuka iiwa 7-DOF arm — from environment setup and robot description integration to real-time vision, motion planning, and trajectory execution. A Python vision node detects a target object and publishes its 3D pose; a C++ MoveIt 2 controller subscribes, plans a collision-free path via the Pilz PTP planner, and executes it on the arm at 225Hz — all visualised live in RViz2 with joint telemetry streamed through PlotJuggler.
# ↑ paragraph shown under "Project Overview"

# ── SKILLS ───────────────────────────────────────────────────────────────────
skills:                        # pill tags shown under "Skills Used" — add or remove lines
  - ROS2
  - C++
  - Python
  - MoveIt 2
  - ros2_control
  - rclcpp
  - rclpy
  - Gazebo
  - RViz2
  - PlotJuggler
  - Motion Planning
  - Inverse Kinematics
  - CMake
  - colcon
  - WSL2
  - Ubuntu

# ── IMAGES ───────────────────────────────────────────────────────────────────
main-image: /preview.png       # banner image at the top of the page (crop ratio 3:1)
# image-position: center 50%  # optional: shift the banner crop, e.g. "center 30%"
# main-image-scale: 1          # optional: zoom the banner image, e.g. 1.2 zooms in
# images_in_column: 2         # optional: how many gallery images appear in the right column (rest flow below)
# images_below_per_row: 2     # optional: columns in the below grid (default 2)
# image_scales:               # optional: width per gallery image in order (100% = fill container)
#   - 100%                    # gallery-1
#   - 100%                    # gallery-2

# ── SPEC BOXES ───────────────────────────────────────────────────────────────
objectives:                    # yellow box — what you set out to do
  - Integrate the ICube Robotics iiwa_ros2 community URDF into a custom ROS2 workspace and bring up ros2_control with JointTrajectoryController running at 225Hz
  - Write a C++ subscriber node to read and log all 7 joint states from /joint_states in real time, establishing core ROS2 pub/sub patterns
  - Write a C++ publisher node to send JointTrajectory commands and move the arm to a target configuration via /iiwa_arm_controller/joint_trajectory
  - Build a Python ROS2 vision node that publishes the detected object pose on /detected_object_pose and draws a visual marker in RViz2
  - Implement a C++ MoveIt 2 controller node that subscribes to the detected pose, invokes the Pilz PTP planner for inverse kinematics and path planning, and executes the resulting trajectory
  - Stream and visualise all 7 joint positions live during execution using PlotJuggler

outcomes:                      # green box — key results and achievements
  - "Built and maintained the full ROS2 workspace from scratch: package structure, CMakeLists.txt dependency management, colcon build system, and sourcing — including resolving a Miniconda/ROS2 Python conflict (conda's Python 3.13 overriding the required system Python 3.10) by prepending /usr/bin to PATH"
  - "Implemented joint_monitor.cpp — a subscriber node demonstrating the core rclcpp callback pattern: std::bind, SharedPtr member variables, and the spin/shutdown lifecycle"
  - Implemented trajectory_sender.cpp — a publisher node that constructs a JointTrajectory message manually and commands the arm to a target joint configuration with a 2-second startup delay
  - Designed and implemented object_detector.py — a Python rclpy node publishing a hardcoded target pose on /detected_object_pose every second alongside a red cube Marker for RViz2 visualisation; architecture is camera-ready — replacing the hardcoded pose with an OpenCV depth camera subscriber requires no changes to downstream nodes
  - Implemented moveit_controller.cpp — receives the detected pose, spins MoveIt 2 in a separate thread to keep callbacks live, calls MoveGroupInterface.setPoseTarget() with the Pilz PTP planner, and executes the planned trajectory; resolved a critical configuration issue where MoveGroupInterface requires kinematics.yaml on its own node's parameter server, not just on move_group — fixed via a custom launch file passing robot_description, robot_description_semantic, and kinematics parameters explicitly
  - Verified smooth S-curve joint trajectories across all 7 joints during execution using PlotJuggler streaming /joint_states at 225Hz

technical:                     # red box — technologies, methods, and implementation details
  - "Robot: Kuka iiwa 7-DOF (ICube Robotics iiwa_ros2 community URDF/Xacro)"
  - "Middleware: ROS2 Humble on Ubuntu 22.04 WSL2"
  - "Control: ros2_control JointTrajectoryController @ 225Hz, fake hardware mode (use_fake_hardware:=true)"
  - "Simulation: Gazebo Classic headless (gzserver); RViz2 for visualisation"
  - "Motion planning: MoveIt 2 + Pilz Industrial Motion Planner (PTP)"
  - "C++ nodes: rclcpp — joint_monitor, trajectory_sender, moveit_controller"
  - "Python node: rclpy — object_detector"
  - "Key packages: moveit_ros_planning_interface, trajectory_msgs, geometry_msgs, visualization_msgs, sensor_msgs"
  - "Architecture: object_detector.py → /detected_object_pose (geometry_msgs/PoseStamped) → moveit_controller.cpp → MoveIt 2 Pilz PTP planner → iiwa_arm_controller @ 225Hz"
  - "Launch: single pick_and_place.launch.py starts simulation, move_group, RViz2, then object_detector (immediately) and moveit_controller (after 15s delay for move_group initialisation)"
  - "Telemetry: PlotJuggler streaming /joint_states; smooth S-curve trajectories confirmed across all 7 joints"
  - "Known issues resolved: Miniconda Python conflict (PATH fix), MoveGroupInterface kinematics parameter scoping (custom launch file), Gazebo GUI crash on WSL2 (headless gzserver)"
  - "GitHub: https://github.com/ebj17"

limitations:                   # blue box — known constraints and future directions
  - Object position is hardcoded in the vision node — a real pipeline would use OpenCV colour segmentation on a depth camera topic to compute the 3D pose.
  - Gazebo GUI disabled on WSL2 due to GPU constraints; physics ran headless with RViz2 as the sole visualiser, preventing full visual validation.
  - No collision objects added to the MoveIt 2 planning scene — the planner cannot currently avoid obstacles in the workspace.
  - "Future work: replace hardcoded pose with live OpenCV detection from a simulated depth camera in Gazebo; add collision objects to the planning scene; extend to a full pick-and-place sequence with gripper control."

# ── GALLERY ──────────────────────────────────────────────────────────────────
# Drop any image named gallery-1.jpg, gallery-2.jpg, gallery-3.jpg etc. into
# this project folder — they appear automatically in order, no edits needed here.
---

<!-- ── WRITTEN CONTENT ──────────────────────────────────────────────────────
     Everything below renders as the body section under the spec boxes.
     Supports full markdown: ## headings, **bold**, - lists, ![img](path), etc.
     Leave blank if you don't need a written section.
─────────────────────────────────────────────────────────────────────────── -->

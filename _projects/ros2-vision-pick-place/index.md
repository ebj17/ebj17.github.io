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
# main-image-ratio: 3/1        # optional: override banner aspect ratio, default 3/1
# images_in_column: 2         # optional: how many gallery images appear in the right column (rest flow below)
# images_below_per_row: 2     # optional: columns in the below grid (default 2)
# image_scales:               # optional: width per gallery image in order (100% = fill container)
#   - 100%                    # gallery-1
#   - 100%                    # gallery-2

# ── SPEC BOXES ───────────────────────────────────────────────────────────────
objectives:                    # yellow box — what you set out to do
  - "Integrate a Kuka iiwa 7-DOF arm into a custom ROS2 workspace with ros2_control running a JointTrajectoryController at 225 Hz."
  - Build a Python vision node that detects a target object and publishes its 3D pose for downstream consumption.
  - Implement a C++ MoveIt 2 controller that subscribes to the detected pose, plans a collision-free path via the Pilz PTP planner, and executes it on the arm.
  - Visualise joint telemetry live during execution using PlotJuggler.

outcomes:                      # green box — key results and achievements
  - "Full ROS2 workspace built from scratch including package structure, CMakeLists.txt, colcon build, and environment sourcing."
  - Implemented joint_monitor.cpp and trajectory_sender.cpp establishing core rclcpp pub/sub and message construction patterns.
  - "Designed object_detector.py publishing a target pose and RViz2 marker; architecture is camera-ready with no downstream changes required to add live OpenCV detection."
  - "Implemented moveit_controller.cpp with MoveIt 2 running in a separate thread; resolved a critical kinematics.yaml parameter scoping issue via a custom launch file."
  - Verified smooth S-curve trajectories across all 7 joints via PlotJuggler streaming at 225 Hz.

technical:                     # red box — technologies, methods, and implementation details
  - "Robot: Kuka iiwa 7-DOF using ICube Robotics iiwa_ros2 community URDF with fake hardware mode."
  - "Middleware: ROS2 Humble on Ubuntu 22.04 WSL2; Gazebo Classic headless with RViz2 for visualisation."
  - "Motion planning: MoveIt 2 with Pilz Industrial Motion Planner (PTP); IK and path planning invoked via MoveGroupInterface.setPoseTarget()."
  - "Architecture: object_detector.py → /detected_object_pose → moveit_controller.cpp → Pilz PTP → JointTrajectoryController at 225 Hz."
  - "Single launch file starts simulation, move_group, RViz2, vision node immediately, and controller after a 15-second delay for move_group initialisation."

limitations:                   # blue box — known constraints and future directions
  - Object pose is hardcoded; a real pipeline would compute it from OpenCV colour segmentation on a depth camera topic.
  - "No collision objects in the MoveIt 2 planning scene, so obstacle avoidance is not currently possible."
  - "Future work: live OpenCV detection from a simulated depth camera, collision objects in the planning scene, and a full pick-and-place sequence with gripper control."

# ── GALLERY ──────────────────────────────────────────────────────────────────
# Drop any image named gallery-1.jpg, gallery-2.jpg, gallery-3.jpg etc. into
# this project folder — they appear automatically in order, no edits needed here.
---

<!-- ── WRITTEN CONTENT ──────────────────────────────────────────────────────
     Everything below renders as the body section under the spec boxes.
     Supports full markdown: ## headings, **bold**, - lists, ![img](path), etc.
     Leave blank if you don't need a written section.
─────────────────────────────────────────────────────────────────────────── -->

---
layout: post
title: Reinforcement Learning for Serial-Chain Manipulator Control
description: Trained a PPO agent to control a 7-DOF Kuka iiwa arm in simulation, achieving end-effector positioning within 2 cm of random targets using a custom Gym environment and two-stage training strategy.
skills:
  - Reinforcement Learning
  - PyBullet
  - OpenAI Gym
  - Stable Baselines3
  - Python
  - Robot Kinematics
  - PPO
  - MLP Policy Design
main-image: /preview.png

objectives:
  - Design a custom simulation environment for a 7-DOF Kuka iiwa serial-chain manipulator in PyBullet.
  - Train a reinforcement learning agent to control end-effector position to reach randomly placed 3D targets.
  - Develop and validate a two-stage training curriculum to improve stability near targets.

outcomes:
  - Achieved end-effector positioning within 2 cm of randomly placed fixed targets in 3D space.
  - Demonstrated stable policy convergence with a custom deep MLP network [512, 512, 256, 128].
  - Two-stage training with angular velocity penalization successfully reduced joint oscillation near targets.

technical:
  - Built a custom OpenAI Gym environment wrapping a PyBullet simulation of a 7-DOF Kuka iiwa arm.
  - Designed a 17-dimensional observation space encoding joint positions, velocities, and target coordinates.
  - Reward function based on negative Euclidean distance between end-effector and target position.
  - Trained on-policy PPO agent using Stable Baselines3 with custom MLP policy [512,512,256,128] and ReLU activations.
  - Stage 2 training introduced an angular velocity penalty term to suppress oscillatory behaviour when near the target.

gallery:
  - /preview.png
---

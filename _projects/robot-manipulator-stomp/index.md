---
layout: post
title: Robot Manipulator Path Planning using STOMP
description: Developed a stochastic trajectory optimisation algorithm in MATLAB for collision-free motion planning of serial-chain manipulators, integrating forward kinematics and end-effector orientation constraints.
skills:
  - MATLAB
  - STOMP
  - Motion Planning
  - Forward Kinematics
  - Product of Exponentials
  - Trajectory Optimisation
  - Obstacle Avoidance
  - Serial-Chain Manipulators
main-image: /preview.png

objectives:
  - Implement the STOMP (Stochastic Trajectory Optimisation for Motion Planning) algorithm in MATLAB for serial-chain manipulators.
  - Integrate forward kinematics using the Product of Exponentials formulation to model the manipulator.
  - Maintain end-effector orientation constraints throughout the motion whilst simulating obstacle avoidance.

outcomes:
  - Successfully generated smooth, collision-free trajectories for serial-chain manipulators using STOMP.
  - Achieved consistent end-effector orientation constraint satisfaction during obstacle avoidance.
  - Validated the algorithm across multiple simulated obstacle configurations.

technical:
  - STOMP implemented in MATLAB — stochastic rollouts used to explore trajectory space and minimise a cost function.
  - Forward kinematics computed using the Product of Exponentials (PoE) formulation for full kinematic chain modelling.
  - Cost function balancing path smoothness, joint limit avoidance, collision penalty, and orientation constraints.
  - Obstacle avoidance handled through signed-distance field evaluation at each trajectory waypoint.

gallery:
  - /preview.png
---

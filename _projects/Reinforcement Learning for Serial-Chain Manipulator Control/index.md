---
layout: post

# ── TITLE & DESCRIPTION ──────────────────────────────────────────────────────
title: 7-DOF Robotic Arm Reach Control via Proximal Policy Optimisation   # h1 shown at the top of the page
description: Designed a custom OpenAI Gym environment for a Kuka iiwa 7-DOF manipulator simulated in PyBullet, and trained a PPO agent to reach a fixed 3D target position. The final policy achieved consistent end-effector convergence with a shaped reward combining euclidean distance minimisation and a joint velocity penalty to encourage smooth, physically plausible motion.
# ↑ paragraph shown under "Project Overview"

# ── SKILLS ───────────────────────────────────────────────────────────────────
skills:                        # pill tags shown under "Skills Used" — add or remove lines
  - Reinforcement Learning
  - PyBullet
  - OpenAI Gym
  - Stable Baselines3
  - Python
  - Robot Kinematics
  - PPO
  - MLP Policy Design

# ── IMAGES ───────────────────────────────────────────────────────────────────
main-image: /preview.png       # banner image at the top of the page (crop ratio 3:1)
# image-position: center 50%  # optional: shift the banner crop, e.g. "center 30%"

# ── SPEC BOXES ───────────────────────────────────────────────────────────────
objectives:                    # yellow box — what you set out to do
  - Build a custom Gymnasium-compatible environment wrapping a PyBullet physics simulation of the Kuka iiwa arm.
  - Define a reward function that drives end-effector convergence while penalising high-velocity joint motion above 3 rad/s.
  - Train a PPO agent with a deep MLP architecture to solve the fixed-target reach task over 4M timesteps.
  - Evaluate policy performance by tracking euclidean distance to target and reward per timestep during testing.

outcomes:                      # green box — key results and achievements
  - Designed the full environment from scratch: 17-dimensional observation space (7 joint positions + 7 joint velocities + 3 target coordinates), 7-dimensional continuous action space mapped to joint angle targets in [-π, π].
  - Trained a two-phase policy: 3M timesteps on base reward, followed by 1M additional steps with the velocity penalty introduced — this staged approach improved motion smoothness without sacrificing convergence speed.
  - Achieved consistent reduction in euclidean distance to target across test episodes, with reward per timestep stabilising at positive values, confirming learned reach behaviour.
  - Identified that the policy was trained on a fixed target only; generalisation to random target positions remains an open challenge and is the most significant limitation of the current model.
  - Future work: curriculum learning from fixed to randomised targets, addition of orientation control for the end-effector, and sim-to-real transfer using domain randomisation.

technical:                     # red box — technologies, methods, and implementation details
  - Robot: Kuka iiwa 7-DOF (PyBullet built-in URDF, fixed base). Simulation at 240 Hz; episode length 6500 timesteps.
  - Observation: 7 joint positions + 7 joint velocities + 3 target XYZ (dim=17). Action: 7 target joint angles ∈ [-π, π] (continuous).
  - Reward: −euclidean_distance(end_effector, target) − velocity_penalty (applied when any joint velocity > 3 rad/s).
  - Algorithm: PPO (Stable Baselines3), MlpPolicy. Network: [512, 512, 256, 128] actor and critic, ReLU — bottleneck architecture to encourage compact state representations.
  - Learning rate: 0.0001; total training: 4M steps (3M base + 1M with penalty). Checkpoints saved every 100k steps; monitored via TensorBoard.
  - Limitation: fixed target only; no orientation control; no sim-to-real pipeline.

# ── GALLERY ──────────────────────────────────────────────────────────────────
# Drop any image named gallery-1.jpg, gallery-2.jpg, gallery-3.jpg etc. into
# this project folder — they appear automatically in order, no edits needed here.
---

<!-- ── WRITTEN CONTENT ──────────────────────────────────────────────────────
     Everything below renders as the body section under the spec boxes.
     Supports full markdown: ## headings, **bold**, - lists, ![img](path), etc.
     Leave blank if you don't need a written section.
─────────────────────────────────────────────────────────────────────────── -->

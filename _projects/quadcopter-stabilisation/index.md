---
layout: post

# ── TITLE & DESCRIPTION ──────────────────────────────────────────────────────
title: LQI Control and Kalman Filter Design for Autonomous Quadcopter Hover   # h1 shown at the top of the page
description: Designed and implemented a full-stack UAV control system for a custom-built quadcopter — from nonlinear dynamics modelling and LQ-optimal controller synthesis to Kalman filter-based sensor fusion and real-time deployment on a BeagleBone Blue embedded platform. The LQI controller eliminated steady-state hover error in simulation; physical gimbal testing validated sensor fusion performance but full autonomous hover could not be completed within the project timeline due to component delays and ESC calibration challenges.
# ↑ paragraph shown under "Project Overview"

# ── SKILLS ───────────────────────────────────────────────────────────────────
skills:                        # pill tags shown under "Skills Used" — add or remove lines
  - MATLAB
  - Simulink
  - LQI Control
  - State-Space Modelling
  - Kalman Filter
  - Sensor Fusion
  - BeagleBone Blue
  - Ansys
  - 3D Printing
  - Embedded Systems

# ── IMAGES ───────────────────────────────────────────────────────────────────
main-image: /preview.png       # banner image at the top of the page (crop ratio 3:1)
image-position: center 60%     # shifts the banner crop vertically — e.g. "center 40%" moves it up

# ── SPEC BOXES ───────────────────────────────────────────────────────────────
objectives:                    # yellow box — what you set out to do
  - Derive a nonlinear 6-DOF quadcopter dynamic model and linearise it into a reduced state-space representation suitable for LQ-optimal control.
  - Design and compare LQR and LQI controllers in MATLAB/Simulink, selecting LQI for its ability to eliminate steady-state hover error under gravity.
  - Implement and tune a discrete Kalman filter for IMU sensor fusion, achieving less than 2 degrees of angular drift over 30 seconds.
  - Deploy the full control stack — discretised controller, motor mixing algorithm, and state observer — onto a BeagleBone Blue for real-time operation.
  - Validate the system through nonlinear Simulink simulation and physical gimbal testing on the assembled drone.

outcomes:                      # green box — key results and achievements
  - Personally responsible for Kalman filter implementation, yaw measurement, R matrix development, and sensor fusion integration — the filter successfully tracked all attitude angles with drift below the 2-degree threshold over 30 seconds.
  - LQI controller demonstrated zero steady-state hover error in full nonlinear simulation with Kalman feedback, outperforming LQR which retained a gravity-induced offset.
  - LQR pitch and roll step responses settled in under 0.5 seconds for a 1 radian input; yaw deliberately tuned slower (~1 second) to account for magnetometer calibration imperfections.
  - Drone frame 3D-printed in PLA and structurally validated via ANSYS FEM with a safety factor above 2, confirmed capable of withstanding operational motor loads.
  - "Physical hover was not achieved: ESC calibration consumed 4 days due to poor documentation, motor shipment delays pushed testing to the final weeks, and controller tuning on the real drone could not be finalised — gimbal testing confirmed correct disturbance response but oscillation at higher gains."
  - "Future work: finalise physical tuning using the established Q-matrix strategy, extend to full trajectory tracking with LQI, and investigate nonlinear/adaptive control for coupled rotational dynamics."

technical:                     # red box — technologies, methods, and implementation details
  - "Plant: nonlinear underactuated MIMO system, 6-DOF, linearised around hover equilibrium; state vector extended to 12 states for LQI with integral error augmentation."
  - "Controllers: LQR (PD-equivalent) and LQI (PI-equivalent); gains computed via Bryson's rule for Q/R initialisation, then iteratively tuned."
  - "Kalman filter: discrete, linear; fusing BeagleBone IMU (accelerometer + gyroscope) and barometer; R matrix tuned from real sensor noise histograms."
  - "Hardware: BeagleBone Blue MCU, Ethix 1507 2800KV brushless motors, HQProp 3x3x3 propellers, custom ESC interface at 50 Hz PWM."
  - "Simulation: full nonlinear Simulink model with Gaussian process and measurement noise; 3D visualisation block included."
  - "FEM: ANSYS Workbench static structural analysis; safety factor > 2 confirmed under operational thrust loads."
  - "Limitation: linearisation valid only near hover — large angle manoeuvres degrade model accuracy; Kalman optimality assumes Gaussian noise which does not fully reflect real IMU characteristics."

# ── GALLERY ──────────────────────────────────────────────────────────────────
# Drop any image named gallery-1.jpg, gallery-2.jpg, gallery-3.jpg etc. into
# this project folder — they appear automatically in order, no edits needed here.
---

<!-- ── WRITTEN CONTENT ──────────────────────────────────────────────────────
     Everything below renders as the body section under the spec boxes.
     Supports full markdown: ## headings, **bold**, - lists, ![img](path), etc.
     Leave blank if you don't need a written section.
─────────────────────────────────────────────────────────────────────────── -->

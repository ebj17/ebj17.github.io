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
main-image-scale: 0.9          # optional: zoom the banner image, e.g. 1.2 zooms in
# main-image-ratio: 3/1        # optional: override banner aspect ratio, default 3/1
# images_in_column: 2         # optional: how many gallery images appear in the right column (rest flow below)
# images_below_per_row: 2     # optional: columns in the below grid (default 2)
image_scales:               # optional: width per gallery image in order (100% = fill container)
   - 70%                    # gallery-1
#   - 100%                    # gallery-2

# ── SPEC BOXES ───────────────────────────────────────────────────────────────
objectives:                    # yellow box — what you set out to do
  - "Build a UAV quadcopter capable of takeoff, hover at 30 ± 5 cm, and landing, with emphasis on control engineering."
  - Derive a nonlinear 6-DOF model, linearise around hover, and implement LQR and LQI controllers.
  - Implement a discrete Kalman filter for IMU sensor fusion, targeting under 2 degrees angular drift over 30 seconds.
  - Deploy and validate the full control stack on a BeagleBone Blue through simulation and gimbal testing.

outcomes:                      # green box — key results and achievements
  - Kalman filter tracked all attitude states below the 2-degree drift threshold, confirmed on physical hardware without motors.
  - LQI eliminated steady-state hover error in nonlinear simulation with Kalman feedback; LQR achieved stability but retained a gravity-induced offset.
  - "Drone frame passed ANSYS FEM validation with a safety factor of 15; assembled mass 448 g, within the 500 g requirement."
  - "Contributions: Kalman filter implementation, tilt-compensated yaw measurement, R matrix development, and sensor fusion integration in Simulink."

technical:                     # red box — technologies, methods, and implementation details
  - "Plant linearised at hover and reduced to 8 states; LQI augments this with integral error terms for Z, φ, θ and ψ."
  - "Kalman filter fuses accelerometer roll and pitch, tilt-compensated magnetometer yaw, gyroscope rates, barometer, and ultrasonic sensor with weighted altitude fusion."
  - "Motor mixing inverts a 4×4 matrix to map controller outputs to individual motor PWM signals, using measured lift and drag coefficients."
  - "Discretised via zero-order hold at Ts = 0.01 s with gains from MATLAB's dlqr; nonlinear simulation includes Gaussian noise, gyroscopic torque, and disturbance injection."

limitations:                   # blue box — known constraints and future directions
  - Linearisation holds only near hover; large-angle dynamics reduce model fidelity.
  - "Kalman optimality assumes Gaussian noise, which real IMU measurements deviate from, especially with motors running."
  - Center of mass sits 8.7 mm below the IMU, introducing unresolved sensor inaccuracies.
  - "Physical hover was not achieved: late motor delivery, 4-day ESC calibration, and unfinished gimbal tuning exhausted the project timeline."
  - Next steps are finalising gimbal tuning and progressing to free-flight LQI trajectory tracking.

# ── GALLERY ──────────────────────────────────────────────────────────────────
# Drop any image named gallery-1.jpg, gallery-2.jpg, gallery-3.jpg etc. into
# this project folder — they appear automatically in order, no edits needed here.
---

<!-- ── WRITTEN CONTENT ──────────────────────────────────────────────────────
     Everything below renders as the body section under the spec boxes.
     Supports full markdown: ## headings, **bold**, - lists, ![img](path), etc.
     Leave blank if you don't need a written section.
─────────────────────────────────────────────────────────────────────────── -->

---
layout: post

# ── TITLE & DESCRIPTION ──────────────────────────────────────────────────────
title: Quadcopter Stabilisation   # h1 shown at the top of the page
description: Designed and deployed an LQI controller on a BeagleBone Blue for quadcopter stabilisation, with a Kalman filter for sensor fusion, a 3D-printed frame validated in Ansys, and full system modelling in MATLAB Simulink.
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
  - Model quadcopter dynamics in state-space representation for controller design.
  - Develop and deploy an LQI controller in MATLAB/Simulink onto a BeagleBone Blue embedded platform.
  - Implement a Kalman filter for sensor fusion and validate the system with real motor characterisation data.

outcomes:                      # green box — key results and achievements
  - Successfully modelled and simulated quadcopter dynamics and achieved stable flight with the deployed LQI controller.
  - Kalman filter reduced process and measurement noise, improving state estimation accuracy.
  - 3D-printed drone frame designed and mechanically validated using FEM analysis in Ansys.

technical:                     # red box — technologies, methods, and implementation details
  - State-space representation of quadcopter dynamics used as the basis for LQI controller synthesis.
  - LQI controller developed in MATLAB/Simulink and deployed to BeagleBone Blue for real-time control.
  - Motor force-thrust data collected experimentally for model validation and control system analysis.
  - Kalman filter designed for sensor fusion combining IMU data to estimate state with reduced noise.

# ── GALLERY ──────────────────────────────────────────────────────────────────
# Drop any image named gallery-1.jpg, gallery-2.jpg, gallery-3.jpg etc. into
# this project folder — they appear automatically in order, no edits needed here.
---

<!-- ── WRITTEN CONTENT ──────────────────────────────────────────────────────
     Everything below renders as the body section under the spec boxes.
     Supports full markdown: ## headings, **bold**, - lists, ![img](path), etc.
     Leave blank if you don't need a written section.
─────────────────────────────────────────────────────────────────────────── -->

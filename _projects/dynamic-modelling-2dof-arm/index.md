---
layout: post

# ── TITLE & DESCRIPTION ──────────────────────────────────────────────────────
title: Dynamic Modelling and PID Control of a 2-DOF Robotic Arm   # h1 shown at the top of the page
description: Derived the full nonlinear equations of motion for a two-link planar manipulator using the Lagrangian-Euler formulation and implemented the dynamic model in MATLAB Simulink. A PID controller tuned via the Ziegler-Nichols method achieved stable closed-loop trajectory tracking across both joints under coupled inertial, Coriolis, and gravitational loading.
# ↑ paragraph shown under "Project Overview"

# ── SKILLS ───────────────────────────────────────────────────────────────────
skills:                        # pill tags shown under "Skills Used" — add or remove lines
  - MATLAB
  - Simulink
  - Lagrangian Dynamics
  - PID Control
  - Robot Dynamics
  - Trajectory Tracking
  - State-Space Modelling

# ── IMAGES ───────────────────────────────────────────────────────────────────
main-image: /preview.png       # banner image at the top of the page (crop ratio 3:1)
# image-position: center 50%  # optional: shift the banner crop, e.g. "center 30%"
# main-image-scale: 1          # optional: zoom the banner image, e.g. 1.2 zooms in
# main-image-ratio: 3/1        # optional: override banner aspect ratio, default 3/1
# images_in_column: 2         # optional: how many gallery images appear in the right column (rest flow below)
# images_below_per_row: 2     # optional: columns in the below grid (default 2)
image_scales:               # optional: width per gallery image in order (100% = fill container)
   - 60%                    # gallery-1
   - 60%                    # gallery-2
   - 100%
   - 100%
   - 60%
# ── SPEC BOXES ───────────────────────────────────────────────────────────────
objectives:                    # yellow box — what you set out to do
  - Derive and simulate the dynamic model of a 2-DOF planar robotic arm using the Lagrangian-Euler method.
  - Design and tune a PID controller to regulate joint angles, benchmarked against a sinusoidal set-point trajectory.

outcomes:                      # green box — key results and achievements
  - Derived the full dynamic model in matrix form, implementing the inertia, Coriolis/centrifugal and gravitational matrices in MATLAB/Simulink.
  - Simulated free-running nonlinear behaviour of both joints over 10 seconds, confirming periodic oscillations consistent with an uncontrolled dynamic system.
  - Successfully implemented two decoupled PID controllers on the linearized system, achieving close set-point tracking after tuning.

technical:                     # red box — technologies, methods, and implementation details
  - Used Denavit-Hartenberg convention to derive homogeneous transformation matrices and extract centre-of-mass position vectors.
  - Applied feedback linearization to decouple the two joints, reducing the system to two independent double-integrator plants with transfer function G(s) = 1/s².
  - "Tuned PID gains using the Ziegler-Nichols second method, with Ku = 9.07 and Tu = 9.56s, yielding Kp = 5.44, Ki = 1.14 and Kd = 6.5 (later increased to 35 to eliminate overshoot)."
  - "MATLAB function block in Simulink computed angular acceleration via left matrix division: d2q = D(Tau − C·dq − G)."

limitations:                   # blue box — known constraints and future directions
  - PID performance on the full nonlinear model was poor; feedback linearization simplifications and joint decoupling introduced unmodelled dynamics.
  - Gains were tuned on the linearized system only; performance on the actual dynamic model was not fully optimised.
  - The decoupling assumption discards cross-joint coupling effects, which remain a source of tracking error in the nonlinear simulation.

# ── GALLERY ──────────────────────────────────────────────────────────────────
# Drop any image named gallery-1.jpg, gallery-2.jpg, gallery-3.jpg etc. into
# this project folder — they appear automatically in order, no edits needed here.
---

<!-- ── WRITTEN CONTENT ──────────────────────────────────────────────────────
     Everything below renders as the body section under the spec boxes.
     Supports full markdown: ## headings, **bold**, - lists, ![img](path), etc.
     Leave blank if you don't need a written section.
─────────────────────────────────────────────────────────────────────────── -->

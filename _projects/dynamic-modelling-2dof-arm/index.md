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

# ── SPEC BOXES ───────────────────────────────────────────────────────────────
objectives:                    # yellow box — what you set out to do
  - Derive equations of motion for a 2-DOF planar manipulator using Lagrangian mechanics and DH parameters.
  - Implement the nonlinear dynamic model in MATLAB Simulink and validate against expected free-response behaviour.
  - Linearise the coupled system via feedback linearisation to enable independent per-joint controller design.
  - Tune and evaluate closed-loop PID trajectory tracking performance on the full nonlinear plant.

outcomes:                      # green box — key results and achievements
  - Derived and implemented the complete D(q)q̈ + C(q,q̇)q̇ + G(q) = τ model from scratch, confirmed by periodic free-response oscillations matching theoretical predictions.
  - Identified and resolved a critical feedback path error — connecting feedback directly from joint angles q₁/q₂ produced instability; rerouting from the dynamic model output restored correct closed-loop behaviour.
  - Reduced joint overshoot by manually increasing the derivative gain from the ZN-tuned value of 6.5 to 35, highlighting PID sensitivity to derivative action in nonlinear systems.
  - Feedback linearisation successfully decoupled both joints into independent double integrators (G(s) = 1/s²), though the inherent simplification introduced unmodelled dynamics that limited tracking precision on the full plant.

technical:                     # red box — technologies, methods, and implementation details
  - DH convention for joint frame definition; homogeneous transformation matrices derived per link.
  - "Lagrangian formulation: kinetic (translational + rotational) and gravitational potential energy per link."
  - "Ziegler-Nichols second method: Ku = 9.07, Tu = 9.56s → Kp = 5.44, Ki = 1.14, Kd = 6.5 (manually refined to Kd = 35)."
  - "Simulink: MATLAB Function block encoding D, C, G matrices; integrator chain for state recovery; dual PID blocks in closed loop."
  - "Limitation: feedback linearisation assumes perfect model knowledge — parameter uncertainty degrades tracking on the physical plant."
  - "Future work: computed torque control or MPC would handle residual nonlinearities more robustly."

# ── GALLERY ──────────────────────────────────────────────────────────────────
# Drop any image named gallery-1.jpg, gallery-2.jpg, gallery-3.jpg etc. into
# this project folder — they appear automatically in order, no edits needed here.
---

<!-- ── WRITTEN CONTENT ──────────────────────────────────────────────────────
     Everything below renders as the body section under the spec boxes.
     Supports full markdown: ## headings, **bold**, - lists, ![img](path), etc.
     Leave blank if you don't need a written section.
─────────────────────────────────────────────────────────────────────────── -->

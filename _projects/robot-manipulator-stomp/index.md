---
layout: post
order: 8

# ── TITLE & DESCRIPTION ──────────────────────────────────────────────────────
title: Robot Manipulator Path Planning using STOMP   # h1 shown at the top of the page
description: Developed a stochastic trajectory optimisation algorithm in MATLAB for collision-free motion planning of serial-chain manipulators, integrating forward kinematics and end-effector orientation constraints.
# ↑ paragraph shown under "Project Overview"

# ── SKILLS ───────────────────────────────────────────────────────────────────
skills:                        # pill tags shown under "Skills Used" — add or remove lines
  - MATLAB
  - STOMP
  - Motion Planning
  - Forward Kinematics
  - Product of Exponentials
  - Trajectory Optimisation
  - Obstacle Avoidance
  - Serial-Chain Manipulators

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
  - Implement the STOMP (Stochastic Trajectory Optimisation for Motion Planning) algorithm in MATLAB for serial-chain manipulators.
  - Integrate forward kinematics using the Product of Exponentials formulation to model the manipulator.
  - Maintain end-effector orientation constraints throughout the motion whilst simulating obstacle avoidance.

outcomes:                      # green box — key results and achievements
  - Successfully generated smooth, collision-free trajectories for serial-chain manipulators using STOMP.
  - Achieved consistent end-effector orientation constraint satisfaction during obstacle avoidance.
  - Validated the algorithm across multiple simulated obstacle configurations.

technical:                     # red box — technologies, methods, and implementation details
  - STOMP implemented in MATLAB — stochastic rollouts used to explore trajectory space and minimise a cost function.
  - Forward kinematics computed using the Product of Exponentials (PoE) formulation for full kinematic chain modelling.
  - Cost function balancing path smoothness, joint limit avoidance, collision penalty, and orientation constraints.
  - Obstacle avoidance handled through signed-distance field evaluation at each trajectory waypoint.

limitations:                   # blue box — known constraints and future directions
  - Placeholder limitation.
  - Placeholder future improvement.

# ── GALLERY ──────────────────────────────────────────────────────────────────
# Drop any image named gallery-1.jpg, gallery-2.jpg, gallery-3.jpg etc. into
# this project folder — they appear automatically in order, no edits needed here.
---

<!-- ── WRITTEN CONTENT ──────────────────────────────────────────────────────
     Everything below renders as the body section under the spec boxes.
     Supports full markdown: ## headings, **bold**, - lists, ![img](path), etc.
     Leave blank if you don't need a written section.
─────────────────────────────────────────────────────────────────────────── -->

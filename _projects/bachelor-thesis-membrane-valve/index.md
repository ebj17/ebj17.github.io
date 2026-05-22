---
layout: post

# ── TITLE & DESCRIPTION ──────────────────────────────────────────────────────
title: Modelling and Control of a Time-Pressure Membrane Valve System for Pharmaceutical Filling
# ↑ h1 shown at the top of the page
description: Bachelor's thesis at DTU — developed a dynamic model and control strategy for a time-pressure membrane valve system used in aseptic pharmaceutical filling, combining system identification, nonlinear modelling, and controller design for precise liquid dispensing.
# ↑ paragraph shown under "Project Overview"

# ── SKILLS ───────────────────────────────────────────────────────────────────
skills:                        # pill tags shown under "Skills Used" — add or remove lines
  - MATLAB
  - Simulink
  - System Identification
  - Nonlinear Control
  - State-Space Modelling
  - PID Control
  - Fluid Dynamics
  - Pharmaceutical Systems

# ── IMAGES ───────────────────────────────────────────────────────────────────
featured: true                 # makes this card span the full grid row on the home page
main-image: /preview.png       # banner image at the top of the page (crop ratio 3:1)
# image-position: center 50%  # optional: shift the banner crop, e.g. "center 30%"
main-image-scale: 0.8          # optional: zoom the banner image, e.g. 1.2 zooms in
# images_in_column: 2         # optional: how many gallery images appear in the right column (rest flow below)
# images_below_per_row: 2     # optional: columns in the below grid (default 2)
# image_scales:               # optional: width per gallery image in order (100% = fill container)
#   - 100%                    # gallery-1
#   - 100%                    # gallery-2

# ── SPEC BOXES ───────────────────────────────────────────────────────────────
objectives:                    # yellow box — what you set out to do
  - Model the dynamic behaviour of the time-pressure membrane valve dispensing system using a grey-box subsystem approach.
  - Develop and simulate advanced nonlinear control strategies capable of outperforming the existing on/off controller.
  - "Benchmark the above strategy against fill precision (±0.2 mm fill accuracy), robustness to pressure fluctuations, and cycle time (3.6s)."

outcomes:                      # green box — key results and achievements
  - A coupled grey-box plant model in Simulink integrating identified actuator, membrane valve, and fluid path subsystem dynamics using physics-inspired data-driven methods.
  - A Sliding Mode Controller was designed and shown to outperform other strategies in tracking accuracy and disturbance robustness under simulated time-varying upstream pressure conditions.
  - The project established a reusable control framework for pharmaceutical dosing systems, providing Novo Nordisk with insights into system nonlinearities and a foundation for future filling line development.

technical:                     # red box — technologies, methods, and implementation details
  - "Piezoelectric actuator model (Xeryon XLA-5) identified via PRBS-based indirect closed-loop frequency domain system identification using Welch's method."
  - Membrane valve characterised experimentally using a custom Arduino-driven load cell and external ADC setup.
  - Flow model obtained through symbolic regression fitted to the orifice equation, with effective area and discharge coefficients as functions of actuator stroke.
  - "Fluid path dynamics modelled as attenuation and time delay. CFD simulations (Star CCM+) used to capture flow behaviour across operating conditions."
  - "Controllers designed in MATLAB/Simulink including PID, LQR/LQI, and Sliding Mode Control."

limitations:                   # blue box — known constraints and future directions
  - A fundamental trade-off between tracking accuracy and actuator compliance was identified. Chattering in the SMC drives the system past actuator velocity limits, motivating investigation into higher-order SMC variations.
  - The model was validated in simulation only. Real-life testing on the full system is required to confirm practical accuracy and expose model uncertainties from subsystem coupling effects.
  - The CFD and coupled plant model cover a single fluid path. Future work should extend this to all manifold channels to assess inter-channel interaction and filling variation.

# ── GALLERY ──────────────────────────────────────────────────────────────────
# Drop any image named gallery-1.jpg, gallery-2.jpg, gallery-3.jpg etc. into
# this project folder — they appear automatically in order, no edits needed here.
---

<!-- ── WRITTEN CONTENT ──────────────────────────────────────────────────────
     Everything below renders as the body section under the spec boxes.
     Supports full markdown: ## headings, **bold**, - lists, ![img](path), etc.
     Leave blank if you don't need a written section.
─────────────────────────────────────────────────────────────────────────── -->

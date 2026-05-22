---
layout: post

# ── TITLE & DESCRIPTION ──────────────────────────────────────────────────────
title: Autonomous Bartender AGV   # h1 shown at the top of the page
description: Designed and built a tracked autonomous robot capable of delivering beverages to assigned seats, using a dual microcontroller setup, PWM motor control, ultrasonic obstacle avoidance, and load cell-triggered initialisation.
# ↑ paragraph shown under "Project Overview"

# ── SKILLS ───────────────────────────────────────────────────────────────────
skills:                        # pill tags shown under "Skills Used" — add or remove lines
  - C++
  - Arduino
  - ESP8266
  - Embedded Systems
  - PWM Motor Control
  - Ultrasonic Sensing
  - Obstacle Avoidance
  - Load Cell Integration
  - Distributed Control

# ── IMAGES ───────────────────────────────────────────────────────────────────
main-image: /preview.png       # banner image at the top of the page (crop ratio 3:1)
# image-position: center 50%  # optional: shift the banner crop, e.g. "center 30%"
# images_in_column: 2         # optional: how many gallery images appear in the right column (rest flow below)
# images_below_per_row: 2     # optional: columns in the below grid (default 2)
image_scales:               # optional: width per gallery image in order (100% = fill container)
   - 100%                    # gallery-1
   - 50%                    # gallery-2

# ── SPEC BOXES ───────────────────────────────────────────────────────────────
objectives:                    # yellow box — what you set out to do
  - Design and build a tracked robot capable of autonomously navigating a bar environment and delivering beverages to assigned seats.
  - Implement distributed control using a dual microcontroller setup for real-time communication and task separation.
  - Integrate FSR weight sensing for automatic drink detection and ultrasonic sensors for obstacle avoidance.

outcomes:                      # green box — key results and achievements
  - Successfully built and demonstrated an autonomous tracked robot with custom 3D-printed mechanical components designed in Siemens NX.
  - Dual Arduino Nano and ESP8266 setup enabled reliable distributed control and wireless communication, signalling the robot when to start and in which direction.
  - FSR weight sensing acted as an initialisation gate, preventing empty dispatch until the bartender had placed the drink.

technical:                     # red box — technologies, methods, and implementation details
  - "Dual microcontroller architecture using Arduino Nano and Wemos D1 Mini ESP8266, communicating via serial and ESP-NOW wireless protocol."
  - PWM motor control coded in C++ with optocoupler speed correction to compensate for motor RPM disparity.
  - Four HC-SR04 ultrasonic sensors with RC low-pass filters enabled obstacle avoidance across four predefined movement directions.
  - FSR circuit using a NE555 timer converting force to frequency, read by the Arduino Nano internal timer to detect drink placement.

limitations:                   # blue box — known constraints and future directions
  - Obstacle avoidance was validated across four predefined directions but not yet deployed in a real bar environment with specific table and seat assignments.
  - Dead reckoning accumulates positional error over time; future work should incorporate encoder-based odometry for improved localisation.
  - Weight sensing was calibrated for a specific glass and volume; future work should generalise this to variable glassware and drink quantities.

# ── GALLERY ──────────────────────────────────────────────────────────────────
# Drop any image named gallery-1.jpg, gallery-2.jpg, gallery-3.jpg etc. into
# this project folder — they appear automatically in order, no edits needed here.
---

<!-- ── WRITTEN CONTENT ──────────────────────────────────────────────────────
     Everything below renders as the body section under the spec boxes.
     Supports full markdown: ## headings, **bold**, - lists, ![img](path), etc.
     Leave blank if you don't need a written section.
─────────────────────────────────────────────────────────────────────────── -->

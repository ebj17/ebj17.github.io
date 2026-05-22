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
  - Design and build a tracked robot capable of autonomously navigating a bar table and delivering beverages to assigned seats.
  - Implement distributed control using a dual microcontroller setup for real-time communication and task separation.
  - Integrate load cell sensing for automatic drink detection and ultrasonic sensors for obstacle avoidance.

outcomes:                      # green box — key results and achievements
  - Successfully built and demonstrated an autonomous tracked AGV 
  - Dual Arduino & ESP8266 setup enabled reliable distributed control and wireless communication signalling to the device when to start operation and to what direction.
  - Load cell integration triggered automatic initialisation upon drink placement, streamlining operation and drinkless delivery.

technical:                     # red box — technologies, methods, and implementation details
  - Dual microcontroller architecture using Arduino Uno and ESP8266.
  - PWM-based motor control programmed in C++ for precise tracked movement.
  - Ultrasonic sensor array used for real-time obstacle detection and avoidance during navigation.
  - Load cell integrated to automatically detect drink placement and trigger the delivery sequence.

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

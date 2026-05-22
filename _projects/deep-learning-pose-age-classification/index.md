---
layout: post

# ── TITLE & DESCRIPTION ──────────────────────────────────────────────────────
title: Deep Learning for Pose and Age Classification   # h1 shown at the top of the page
description: Built an OpenPose-based posture recognition classifier and trained a CNN for real-time facial age classification from live video, integrating OpenCV for image processing and prediction display.
# ↑ paragraph shown under "Project Overview"

# ── SKILLS ───────────────────────────────────────────────────────────────────
skills:                        # pill tags shown under "Skills Used" — add or remove lines
  - Python
  - Deep Learning
  - OpenPose
  - CNN
  - OpenCV
  - Jupyter Notebook
  - Computer Vision
  - PyTorch

# ── IMAGES ───────────────────────────────────────────────────────────────────
main-image: /preview.png       # banner image at the top of the page (crop ratio 3:1)
# image-position: center 50%  # optional: shift the banner crop, e.g. "center 30%"
# main-image-scale: 1          # optional: zoom the banner image, e.g. 1.2 zooms in
# main-image-ratio: 3/1        # optional: override banner aspect ratio, default 3/1
images_in_column: 3         # optional: how many gallery images appear in the right column (rest flow below)
# images_below_per_row: 2     # optional: columns in the below grid (default 2)
# image_scales:               # optional: width per gallery image in order (100% = fill container)
#   - 100%                    # gallery-1
#   - 100%                    # gallery-2

# ── SPEC BOXES ───────────────────────────────────────────────────────────────
objectives:                    # yellow box — what you set out to do
  - Develop a rule-based standing/sitting classifier using hip-knee angle geometry derived from OpenPose keypoints.
  - Train a convolutional neural network for facial age classification using live video input.

outcomes:                      # green box — key results and achievements
  - Deployed a working pose classifier with skeleton overlay for real-time posture recognition from video.
  - CNN achieved 77% overall test accuracy for facial age classification, with real-time prediction display on live camera feed.
  - Full pipeline from frame capture to classification and visualisation integrated in Jupyter Notebook.

technical:                     # red box — technologies, methods, and implementation details
  - "Rule-based standing/sitting classifier computed hip-to-knee angles from OpenPose keypoints, with standing defined above 70° and sitting below 40°."
  - "CNN trained for multi-class facial age classification on 33,485 images across 5 age bands, with live camera feed prediction."
  - OpenCV used for frame capture, image preprocessing, and real-time overlay of classification results.

limitations:                   # blue box — known constraints and future directions
  - "Age model is biased toward the 0–18 class due to training set imbalance; most other age bands scored below 60% precision."
  - Pose classifier uses fixed angle thresholds and was validated on two images only, limiting generalisation to varied camera angles or partial occlusion.
  - "Future work: collect balanced age-class data, deepen CNN architecture, and extend pose rules to additional postures beyond sitting/standing."

# ── GALLERY ──────────────────────────────────────────────────────────────────
# Drop any image named gallery-1.jpg, gallery-2.jpg, gallery-3.jpg etc. into
# this project folder — they appear automatically in order, no edits needed here.
---

<!-- ── WRITTEN CONTENT ──────────────────────────────────────────────────────
     Everything below renders as the body section under the spec boxes.
     Supports full markdown: ## headings, **bold**, - lists, ![img](path), etc.
     Leave blank if you don't need a written section.
─────────────────────────────────────────────────────────────────────────── -->

---
layout: post
order: 4

# ── TITLE & DESCRIPTION ──────────────────────────────────────────────────────
title: Stereo Depth Estimation Pipeline with ROS2 and OpenCV   # h1 shown at the top of the page
description: Built a ROS2 stereo vision pipeline from scratch in Python — camera calibration, rectification, and SGBM depth estimation — demonstrated on real da Vinci Xi surgical footage (StereoMIS dataset) and validated on KITTI. Compared classical SGBM against RAFT-Stereo to demonstrate that learned stereo matching dramatically outperforms block matching on low-texture surgical tissue.
# ↑ paragraph shown under "Project Overview"

# ── SKILLS ───────────────────────────────────────────────────────────────────
skills:                        # pill tags shown under "Skills Used" — add or remove lines
  - ROS2
  - Python
  - OpenCV
  - Stereo Vision
  - Camera Calibration
  - SGBM
  - Depth Estimation
  - cv_bridge
  - message_filters
  - RAFT-Stereo
  - PyTorch
  - CUDA

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
#   - 100%                    # gallery-3
#   - 100%                    # gallery-4

# ── SPEC BOXES ───────────────────────────────────────────────────────────────
objectives:                    # yellow box — what you set out to do
  - "Build a complete stereo vision pipeline in ROS2: camera calibration, stereo rectification, and disparity-based depth estimation from scratch using OpenCV."
  - Demonstrate the pipeline on real da Vinci Xi surgical endoscope footage from the StereoMIS dataset.
  - Validate pipeline correctness by running the same SGBM algorithm on KITTI Stereo 2012 benchmark data.
  - Compare classical block matching (SGBM) against a learned stereo matcher (RAFT-Stereo) on the same surgical frame to isolate the algorithm as the limiting factor.

outcomes:                      # green box — key results and achievements
  - "Three-node ROS2 package (fake_camera, depth_node, calibration_node) with ApproximateTimeSynchronizer for matched stereo pair processing."
  - Working rectification and SGBM disparity pipeline running at ~30 fps end to end.
  - "Clean, dense disparity maps on KITTI data confirming pipeline correctness — noisy results on StereoMIS correctly attributed to the algorithm class, not the implementation."
  - Side-by-side SGBM vs RAFT-Stereo comparison on the same surgical frame demonstrating dramatically cleaner depth from learned matching.

technical:                     # red box — technologies, methods, and implementation details
  - "Architecture: fake_camera.py publishes split stereo frames to /left/image and /right/image; depth_node.py subscribes via ApproximateTimeSynchronizer, rectifies with precomputed cv2.remap maps, and computes disparity with StereoSGBM (blockSize=5, uniquenessRatio=10, speckleWindowSize=100, speckleRange=2, disp12MaxDiff=1, MODE_SGBM_3WAY)."
  - Calibration loaded from StereoMIS-provided StereoCalibration.ini (focal lengths, optical centers, distortion coefficients, R, T).
  - KITTI validation uses pre-rectified images with the exact same SGBM pipeline — only the rectification step is skipped.
  - "RAFT-Stereo inference run on RTX 4060 Laptop GPU using pretrained raftstereo-middlebury.pth weights (~3.7s per frame)."
  - "Dataset: StereoMIS (Hayoz & Allan, 2023) — da Vinci Xi stereo endoscope, 11 sequences, in-vivo porcine."

limitations:                   # blue box — known constraints and future directions
  - Classical SGBM fails on low-texture surgical tissue — specular highlights and uniform surfaces create too many ambiguous pixel matches.
  - No ground truth depth available for quantitative evaluation on StereoMIS.
  - fake_camera.py replays pre-recorded video rather than subscribing to a live stereo camera.
  - "Next steps: WLS disparity post-filtering, full RAFT-Stereo integration as a ROS2 node, and extending to visual odometry with feature tracking and camera motion estimation."

# ── GALLERY ──────────────────────────────────────────────────────────────────
# Drop any image named gallery-1.jpg, gallery-2.jpg, gallery-3.jpg etc. into
# this project folder — they appear automatically in order, no edits needed here.
---

<!-- ── WRITTEN CONTENT ──────────────────────────────────────────────────────
     Everything below renders as the body section under the spec boxes.
     Supports full markdown: ## headings, **bold**, - lists, ![img](path), etc.
     Leave blank if you don't need a written section.
─────────────────────────────────────────────────────────────────────────── -->

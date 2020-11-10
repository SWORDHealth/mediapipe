## Instructions to build a new AAR (using wrist therapy as example)

Building AAR:
bazel build -c opt --host_crosstool_top=@bazel_tools//tools/cpp:toolchain --fat_apk_cpu=arm64-v8a --linkopt="-s" //mediapipe/examples/android/src/java/com/google/mediapipe/apps/wristtherapy:hand_tracking_aar

Add ",armeabi-v7a" as argument to --fat_apk_cpu to compile to the other common mobile CPU
architecture

Removing the linkopt argument will include debug-related symbolic links (and will bring the AAR size
to over 100MB)

Generating new binary graph:
bazel build -c opt mediapipe/graphs/hand_tracking:hand_tracking_mobile_gpu_binary_graph


---
layout: default
title: Home
nav_order: 1
---

![MediaPipe](docs/images/mediapipe_small.png)

--------------------------------------------------------------------------------

## Live ML anywhere

[MediaPipe](https://google.github.io/mediapipe/) offers cross-platform, customizable
ML solutions for live and streaming media.
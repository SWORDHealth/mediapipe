# Copyright 2019 The MediaPipe Authors.
#
# Licensed under the Apache License, Version 2.0 (the "License");
# you may not use this file except in compliance with the License.
# You may obtain a copy of the License at
#
#      http://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing, software
# distributed under the License is distributed on an "AS IS" BASIS,
# WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
# See the License for the specific language governing permissions and
# limitations under the License.

load(
    "//mediapipe/framework/tool:mediapipe_graph.bzl",
    "mediapipe_binary_graph",
)

licenses(["notice"])

package(default_visibility = ["//visibility:public"])

exports_files(glob([
    "*.pbtxt",
]))

cc_library(
    name = "mobile_calculators",
    deps = [
        "//mediapipe/calculators/core:constant_side_packet_calculator",
        "//mediapipe/calculators/core:flow_limiter_calculator",
        "//mediapipe/calculators/core:packet_presence_calculator",
        "//mediapipe/wrist_therapy/graphs/subgraphs:hand_renderer_gpu",
        "//mediapipe/modules/hand_landmark:hand_landmark_tracking_gpu",
    ],
)

mediapipe_binary_graph(
    name = "hand_tracking_mobile_gpu_binary_graph",
    graph = "hand_tracking_mobile.pbtxt",
    output_name = "hand_tracking_mobile_gpu.binarypb",
    deps = [":mobile_calculators"],
)
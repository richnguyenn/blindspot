# Blindspot: Helping Assistive Robots See Partially Hidden People

COMP SCI 4ZP6 Capstone, Team 11 · Supervisor: Dr. Gary Bone (Mechanical Engineering, McMaster University)

## Overview

Assistive robots can't safely work around people unless they know the 3D space each person occupies, including body parts hidden behind furniture, objects or other people. Standard skeleton trackers give rough stick figures and fail under occlusion.

Blindspot takes colour point clouds from a Kinect v2 sensor (live or recorded PCD files) and estimates each person's full body volume, including hidden limbs. It outputs 15 labelled capsules per person with a configurable safety margin. When confidence is low, volumes are enlarged rather than shrunk.

**Pipeline:** acquisition → preprocessing (floor/wall removal) → person segmentation → keypoint seeding → tracking → SMPL body fitting with free-space constraints → capsule output and 3D viewer.

## Tech Stack

- **C++17:** PCL, Eigen (point cloud processing and geometry)
- **Python 3.11:** PyTorch + SMPL (body fitting), ONNX Runtime (pose estimation), Open3D (viewer)
- **Build/CI:** CMake, vcpkg, MSVC, GitHub Actions
- **Platform:** Windows 10/11

## Repository Structure

```
/src        Source code (io, preprocessing, segmentation, body_model, occlusion, viz)
/tests      Unit tests
/data       Synthetic sample PCDs (Git LFS)
/docs       Course deliverables
/meetings   Meeting records
```

## Getting Started

Build and run instructions coming soon.

## Team

Kenny Zhao (Project Manager) · William Guo · Eric Park · Bruce Wang · Richard Nguyen · Alan Zhou

## License

[MIT](LICENSE), pending confirmation with Dr. Bone.

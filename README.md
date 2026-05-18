# YOLOv5-RealSense
  Object detection with distance estimation using YOLOv5 and Intel RealSense Depth Cameras.

## Overview

YOLOv5-RealSense integrates Ultralytics YOLOv5 with the Intel RealSense D435i (and compatible) depth cameras. This workspace runs real-time object detection and calculates the distance to the identified objects using the camera's depth sensor.

It contains custom scripts `realDetect.py` and `detect_j.py` directly adapted from the YOLOv5 pipeline to support the `pyrealsense2` API for handling RGB-D data streams seamlessly.

## Prerequisites

- **Hardware:** Intel RealSense D435i Camera
- **OS:** Linux / Windows / macOS (wherever `pyrealsense2` is supported)
- **Python:** >= 3.8.0
- **PyTorch:** >= 1.8

## Installation

1. Clone the repository and navigate into it:
   ```bash
   git clone <your-repo-link>
   cd YOLOv5-RealSense
   ```

2. Install the required dependencies:
   ```bash
   pip install -r requirements.txt
   ```

*Note: Ensure `pyrealsense2` is installed correctly for your platform.*

## Usage

This extension adds real-time robust depth sensing via RealSense directly to YOLOv5 inference.

### `detect_realsense.py`
Connect your RealSense camera and run:

```bash
python detect_realsense.py --weights yolov5s.pt --view-img
```

**Features added:**
- Starts the RealSense pipeline for both color and depth streams.
- Performs YOLO inference on color frames in real-time.
- Captures depth dynamically from the resulting bounding boxes and displays the object distance in inches and centimeters natively on the view screen.

---
## Acknowledgements

- Built on top of [YOLOv5 🚀](https://github.com/ultralytics/yolov5) by Ultralytics.
- Distance calculations utilize the [Intel RealSense SDK 2.0](https://github.com/IntelRealSense/librealsense).

*For additional standard YOLOv5 instructions (training, inference parameters, exports), please refer to the [YOLOv5 Documentation](https://docs.ultralytics.com/yolov5/).*

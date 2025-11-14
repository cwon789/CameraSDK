# SDK for Private Use

## ROS2 Foxy Compatibility Patches (Ubuntu 20.04)

### Modified Files
- `linux/Sample/ros2/lx_camera_node_ws/src/lx_camera_ros/CMakeLists.txt`
- `linux/Sample/ros2/lx_camera_node_ws/src/lx_camera_ros/src/lx_camera/lx_camera.cpp`
- `linux/Sample/ros2/lx_camera_node_ws/src/lx_camera_ros/src/lx_localization/lx_localization.cpp`

### Changes
#### CMakeLists.txt
- **ROS2 Foxy API Compatibility**: Replaced `rosidl_get_typesupport_target()` (Humble+) with `rosidl_target_interfaces()` for ROS2 Foxy compatibility
- **SDK Include Path**: Added `${PROJECT_SOURCE_DIR}/../../../../../SDK/include` to include directories to resolve missing header files (`lx_camera_define.h`, `lx_camera_application.h`)
- **CMake Version Range**: Updated `cmake_minimum_required(VERSION 3.10...3.18)` to suppress PCL deprecation warnings

#### lx_camera.cpp
- **Deprecated Header Removal**: Removed `#include "sensor_msgs/point_cloud_conversion.hpp"` (deprecated in ROS2 Foxy, unused in code)

#### lx_localization.cpp
- **String Initialization Fix**: Changed `algo_ver` initialization from string literal `"0.0.0"` to `nullptr` with null-check logic to avoid ISO C++ write-strings warning

### Build Instructions for ROS2 Foxy
```bash
cd linux/Sample/ros2/lx_camera_node_ws
colcon build
```

### Requirements
- Ubuntu 20.04
- ROS2 Foxy
- PCL (Point Cloud Library)
- OpenCV

---

# Release Notes

## SDK V2.4.50
- support new calibration algo,LX_PTR_2D_NEW_INTRIC_PARAM and LX_PTR_3D_NEW_INTRIC_PARAM
- fix some bugs,and add some features
- linux version of cameraviewer
- cameraViewer supports restricted access to the camera device for devices connected via the SDK

## LxDataProcess V1.3.30
- fix some bugs

- Add python3 api whl file

## SDK V2.4.38
- Support S10 series
- Fix some bugs
- Add some features

## LxDataProcess V1.2.27
- Fix some bugs

## Firmware
- Fix some bugs

## SDK V2.4.32
- Support T2 series and S3 series
- Fix bugs related to device discovery and opening

## LxDataProcess V1.2.21
- Support T2 series and S3 series

## Firmware
- Fix some bugs

## SDK V2.4.23
- Fix some bugs
- Add some configuration capabilities

## LxDataProcess 1.2.19
- Fix some bugs

## Firmware
- Reduced data processing

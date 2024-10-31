---
icon: fas fa-robot
order: 1
title: Recording System
---

# Robotic Platform

The data recording system is built on a holonomic robotic platform designed for reliable, synchronized, and efficient data capture, essential for evaluating SLAM algorithms across various environments. Equipped with a range of sensors—including cameras, IMUs, and a ground truth system—the platform is configured for optimal data quality and comprehensive environmental coverage.

![Robotic Recording Overview](assets/images/system_overview2.png)

The robotic platform is based on a modified prototype of a robotic lawn mower, with the sensor suite and onboard computing resources mounted on top. Driven by two large rear wheels for propulsion and two smaller front wheels for stability, the platform is sensitive to surface conditions, which can lead to vibrations when navigating uneven terrain. The platform is manually controlled via a game controller and operates at a consistent speed of 0.5 m/s to minimize dynamic influence on sensors during data acquisition. An external light source is also mounted to facilitate night-time recording.

# Sensors

The robotic platform is outfitted with carefully selected sensors to provide multi-modal data, enabling robust SLAM evaluation under diverse conditions. The sensors include cameras, IMUs, and a precision ground truth system. Below is an overview of the sensors and their specifications.

| **Sensor**                  | **Modality**  | **Characteristics**                                                                             | **Data Rate [Hz]** |
| --------------------------- | ------------- | ----------------------------------------------------------------------------------------------- | ------------------ |
| **Joy IT Pi Camera**        | Camera        | Resolution: 640 x 480 RGB, Rolling Shutter, FoV: 160°/122°/89.5°, Wide Angle, Fixed Focus       | 30                 |
| **Intel RealSense D435i**   | Camera        | Resolution: 640 x 480, Global Shutter                                                           | 30                 |
|                             |               | RGB: FOV: 77°/69°/42°, Rolling Shutter, Fixed Focus                                             |                    |
|                             |               | Depth: Active IR Stereo, 0.2m - 10m, FoV: 94°/86°/57°                                           |                    |
|                             | IMU           | 6 DoF: Accelerometer, Gyrometer                                                                 | 100, 200           |
| **Intel RealSense T265**    | Camera        | Resolution: 848 x 800 Monochrome, Global Shutter, FoV: 160° Diagonal, Fisheye Lens, Fixed Focus | 30                 |
|                             | IMU           | 6 DoF: Accelerometer, Gyrometer                                                                 | 65, 200            |
| **VectorNav VN100**         | IMU           | 9 DoF: Accelerometer, Gyrometer, Magnetometer                                                   | 65                 |
| **Leica TS16 Totalstation** | Laser Tracker | 3 DoF Position, Accuracy: 1mm + 1.5 ppm                                                         | 2 - 5              |

## Cameras

![Camera Perspectives](assets/images/cam_triple_horizontal.png)

The cameras are the core of the dataset, capturing RGB, depth, and monocular perspectives to provide visual data from diverse angles. These include the Joy IT Pi Camera (budget-friendly wide-angle RGB), Intel RealSense D435i (RGB and depth with IMU integration), and Intel RealSense T265 (fisheye monochrome stereo for tracking). Each camera offers specific advantages, from high FoV for environmental coverage to motion-resistant global shutters, maximizing data relevance for SLAM applications.

## IMUs

The robotic platform includes both internal and external IMUs, enhancing data accuracy by capturing detailed motion and orientation. The Intel RealSense D435i and T265 cameras each include a 6 DoF IMU, while the VectorNav VN100 provides high-precision 9 DoF data, including magnetic orientation for full environmental awareness. The VN100, mounted on the rotation axis, delivers stable motion data even in rough terrain, supporting reliable sensor fusion.

# Ground Truth

For ground truth data, the Leica TS16 Totalstation tracks the precise position of a prism on the platform with millimeter-level accuracy. It records 3 DoF positional data at 2-5 Hz, enabling accurate validation of sensor positioning and system accuracy.

# Calibration

Accurate calibration of each sensor is essential for reliable data fusion. The calibration involved the Kalibr toolbox for camera and IMU alignment, covering intrinsic and extrinsic parameters for each camera and IMU. Additionally, CAD-based calibration aligned the sensors with the prism, ensuring compatibility with the ground truth system.

# Data Recording

The system architecture is designed for efficient data capture, storage, and synchronization, facilitating SLAM evaluation. Dedicated Intel NUC and Raspberry Pi devices process the sensor data, with a Raspberry Pi acting as an NTP server for precise time synchronization across the network. The GNSS and NTP protocols ensure nanosecond-level accuracy, supporting accurate temporal alignment across all recorded data.

![Data Recording and Time Synchronization](assets/images/system_architecture.png)

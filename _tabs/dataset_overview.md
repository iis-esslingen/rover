---
title: Dataset Overview
author: Fabian Schmidt
date: 2024-10-31
category: Jekyll
layout: post
---

# Locations

This dataset includes recordings from five distinct outdoor locations, captured at the campus of Esslingen University and in a private garden. Each environment was selected to present unique challenges for SLAM algorithm evaluation, offering diverse conditions in terms of layout, vegetation, lighting, and stability. By encompassing a broad range of real-world scenarios—from compact urban green spaces to expansive natural areas—the dataset supports comprehensive testing and development of SLAM systems, allowing researchers to evaluate and improve adaptability in varied settings.

## Location Characteristics

Each environment was selected based on several important criteria, which help in evaluating the performance and robustness of SLAM systems. The following characteristics offer insight into how each location supports specific challenges and testing conditions:

- **Size:** The overall area size influences the scope of navigation. Large areas allow for testing long operational times and path optimization, while smaller areas focus on precision in confined spaces.
  
- **Shape Complexity:** Simple shapes (e.g., squares) are easier for robots to navigate, whereas more complex shapes introduce challenges with frequent turns and directional changes.

- **Slope Inclination:** Varying terrain slopes can influence sensor data, particularly from cameras. Steep slopes may shift sensors’ fields of view upward or downward, affecting the range of detected features.

- **Long-Term Stability:** Environmental stability over time affects the consistency of visual cues. Seasonal changes, growth of vegetation, or new obstacles may impact the reliability of location-based SLAM systems.

- **Vegetation:** Trees, shrubs, and other vegetation provide natural landmarks but can introduce occlusions and unique navigation obstacles. Dense vegetation areas demand robust feature detection and tracking capabilities.

- **Brightness:** Ambient lighting levels, from bright open spaces to shaded areas, affect visual perception systems. Dynamic lighting changes, such as shifting cloud cover, test a system's ability to adapt to varying brightness levels.

| **Location** | **Size [sqm]** | **Shape Complexity** | **Slope Inclination** | **Long-Term Stability** | **Vegetation** | **Brightness** |
| ------------ | -------------- | -------------------- | --------------------- | ----------------------- | -------------- | -------------- |
| Park         | 250            | High                 | Medium                | Medium                  | High           | Medium         |
| Campus Small | 75             | Medium               | None                  | High                    | Low            | Low            |
| Campus Large | 500            | Low                  | None                  | High                    | Low            | High           |
| Garden Small | 100            | Medium               | None                  | Medium                  | Medium         | Low            |
| Garden Large | 250            | High                 | Low                   | Low                     | High           | High           |


## Park
![Park]({{ site.baseurl }}/assets/images/park.jpg)

The *Park* location is a natural area with moderate slopes and varied vegetation, including trees and bushes. This setting provides both natural obstacles and landmarks, aiding navigation but also occasionally obstructing movement. The ambient brightness varies, adding to the challenge of dynamic environmental conditions for SLAM evaluations.

## Campus Small
![Campus Small]({{ site.baseurl }}/assets/images/campus_small.jpg)

*Campus Small* is a compact lawn adjacent to a building, featuring minimal vegetation and a reflective glass surface that introduces visual localization challenges. The surrounding structures cast shadows, creating a low-brightness environment suited for controlled testing scenarios.

## Campus Large
![Campus Large]({{ site.baseurl }}/assets/images/campus_large.jpg)

Situated on a rooftop, *Campus Large* offers an expansive area with minimal vegetation and an unobstructed horizon-like view. The stable brightness and few visual landmarks provide a distinct testing ground for navigation in open spaces with limited environmental cues.

## Garden Small
![Garden Small]({{ site.baseurl }}/assets/images/garden_small.jpg)

*Garden Small* is a shaded garden area surrounded by buildings and a uniform wall on one side. It has moderate vegetation density and reduced brightness, making it challenging for consistent tracking due to limited visual variety.

## Garden Large
![Garden Large]({{ site.baseurl }}/assets/images/garden_large.jpg)

The *Garden Large* location is a traditional garden with dense vegetation, low incline, and ample light. This visually rich setting enhances the difficulty of navigation and path-planning, with varied vegetation providing both complex landmarks and obstacles for localization.

# Recordings

The dataset captures the environmental variations of each location across different seasons and weather conditions, highlighting how factors such as vegetation, brightness, and lighting influence the robot's performance. Each location was recorded in diverse weather conditions—including sunny, cloudy, and windy days—and at various times of day, from dusk to night, to assess sensor performance under varying light levels.

![Dataset Preview]({{ site.baseurl }}/assets/images/dataset_preview2.png)

The table below provides a summary of the recordings and their associated environmental conditions, while the image above illustrates seasonal changes and different lighting conditions within the dataset. This variety allows researchers to evaluate SLAM systems in realistic outdoor scenarios, capturing the challenges presented by changing environmental factors.

To ensure consistency across recordings, we used a standardized route referred to as the *Perimeter* scenario. In this scenario, the robot follows the edge of the lawn area, completing three full rounds. Each round has slight trajectory variations and partial overlaps with the previous ones, creating realistic spatial coverage and enhancing the dataset with natural path variations. This approach enables the analysis of how environmental changes over time affect localization accuracy along a familiar path. It also supports loop-closing opportunities to maintain accurate long-term localization and promotes robust long-term mapping by capturing the same environment repeatedly under diverse conditions.

Note: A winter recording for the Park location is not included due to heavy slippage caused by the slope inclination. Additionally, the Campus Large Summer recording lacks PiCam data, while the Campus Large Dusk and Garden Small Winter recordings do not contain data from the D435i internal IMU.

| **Location**     | **Date**              | **Distance [m]** | **Duration [s]** | **Windy** | **Sunny** | **Cloudy** | **Dusk** | **Night** | **+ Light** |
| ---------------- | --------------------- | ---------------- | ---------------- | --------- | --------- | ---------- | -------- | --------- | ----------- |
| **Park**         | 2023-07-31 - 11:28:49 | 164.24           | 422.71           |           |           | x          |          |           |             |
|                  | 2023-11-07 - 16:07:01 | 170.47           | 482.32           | x         |           | x          |          |           |             |
|                  | 2024-04-14 - 14:56:43 | 171.46           | 446.40           |           | x         | x          |          |           |             |
|                  | 2024-05-08 - 12:00:23 | 183.00           | 466.35           |           |           | x          |          |           |             |
|                  | 2024-05-13 - 21:09:16 | 182.67           | 463.27           |           |           |            | x        |           |             |
|                  | 2024-05-13 - 21:28:35 | 179.75           | 457.37           |           |           |            |          | x         |             |
|                  | 2024-05-24 - 21:53:02 | 172.13           | 443.30           |           |           |            |          |           | x           |
| **Campus Small** | 2023-09-11 - 09:39:05 | 155.27           | 403.77           |           | x         |            |          |           |             |
|                  | 2023-11-23 - 15:41:16 | 156.16           | 405.85           |           |           | x          |          |           |             |
|                  | 2024-02-19 - 15:11:40 | 149.77           | 379.42           |           |           | x          |          |           |             |
|                  | 2024-04-14 - 14:34:47 | 151.87           | 387.61           |           | x         | x          |          |           |             |
|                  | 2024-05-07 - 12:12:13 | 156.28           | 400.38           |           |           | x          |          |           |             |
|                  | 2024-05-08 - 20:55:29 | 157.31           | 399.63           |           |           |            | x        |           |             |
|                  | 2024-05-08 - 21:18:04 | 155.07           | 397.84           |           |           |            |          | x         |             |
|                  | 2024-05-24 - 22:09:50 | 153.60           | 395.17           |           |           |            |          |           | x           |
| **Campus Large** | 2023-07-20 - 13:50:02 | 384.92           | 1035.23          | x         |           | x          |          |           |             |
|                  | 2023-11-07 - 15:27:56 | 381.24           | 978.09           | x         |           | x          |          |           |             |
|                  | 2024-01-27 - 10:19:38 | 289.71           | 740.68           |           | x         |            |          |           |             |
|                  | 2024-04-14 - 14:01:26 | 368.39           | 928.93           |           | x         | x          |          |           |             |
|                  | 2024-09-24 - 19:36:44 | 277.29           | 707.99           |           |           | x          | x        |           |             |
|                  | 2024-09-24 - 19:55:55 | 277.81           | 692.71           |           |           |            |          | x         |             |
|                  | 2024-09-24 - 20:09:32 | 274.46           | 695.15           |           |           |            |          |           | x           |
|                  | 2024-09-25 - 14:27:59 | 277.19           | 701.29           | x         |           | x          |          |           |             |
| **Garden Small** | 2023-08-18 - 14:27:36 | 116.36           | 323.18           | x         | x         |            |          |           |             |
|                  | 2023-09-15 - 16:37:27 | 116.34           | 320.92           |           |           | x          |          |           |             |
|                  | 2024-01-13 - 09:17:46 | 113.30           | 330.22           |           |           | x          |          |           |             |
|                  | 2024-04-11 - 16:52:39 | 124.79           | 338.36           |           | x         |            |          |           |             |
|                  | 2024-05-29 - 17:24:28 | 121.35           | 310.83           |           |           | x          |          |           |             |
|                  | 2024-05-29 - 21:14:15 | 124.21           | 312.69           |           |           |            | x        |           |             |
|                  | 2024-05-29 - 21:35:57 | 122.68           | 315.26           |           |           |            |          | x         |             |
|                  | 2024-05-29 - 21:47:30 | 120.04           | 307.88           |           |           |            |          |           | x           |
| **Garden Large** | 2023-08-18 - 14:54:17 | 167.66           | 452.58           | x         | x         |            |          |           |             |
|                  | 2023-11-03 - 11:23:58 | 170.41           | 446.20           |           |           | x          |          |           |             |
|                  | 2024-01-13 - 10:02:43 | 162.28           | 415.65           |           |           | x          |          |           |             |
|                  | 2024-04-11 - 17:06:47 | 164.99           | 431.86           |           | x         |            |          |           |             |
|                  | 2024-05-29 - 17:13:26 | 150.31           | 377.22           |           |           | x          |          |           |             |
|                  | 2024-05-29 - 21:20:14 | 151.83           | 385.43           |           |           |            | x        |           |             |
|                  | 2024-05-30 - 21:50:12 | 150.53           | 380.96           |           |           |            |          | x         |             |
|                  | 2024-05-30 - 22:03:19 | 151.80           | 383.83           |           |           |            |          |           | x           |


# Data Description

## Raw Data Overview

The dataset contains raw data organized by sequence directories, with sensor-specific subdirectories for easy access. Each sensor's data is stored in its respective format, with images, IMU data, and ground truth recordings structured as follows:

- Sequence Directory
    - intelrealsense_D435i
        - rgb_img
          - timestamp.png
          - ...
        - depth_img
          - timestamp.png
          - ...
        - accel.csv
        - gyro.csv
    - intelrealsense_T265
      - cam_left
        - timestamp.png
        - ...
      - cam_right
        - timestamp.png
        - ...
      - accel.csv
      - gyro.csv
      - pose.csv
    - picam
      - timestamp.png
      - ...
    - vn100
      - vn100.csv
    - groundtruth
      - groundtruth.csv

## Rosbag Generation

We provide scripts to convert raw data into ROS bag files, available [here](link-to-github). Note that the IMU publishing rate for Intel RealSense D435i and T265 depends on the snychronization strategy of acceleromenter and gyrometer. The generated topics include the following data streams:

| **Sensor**            | **ROS Topic**        | **ROS Message Type** | **Publish Rate [Hz]** |
| --------------------- | -------------------- | -------------------- | --------------------- |
| Intel RealSense D435i | /d435i/rgb_image     | sensor_msgs/Image    | 30                    |
|                       | /d435i/depth_image   | sensor_msgs/Image    | 30                    |
|                       | /d435i/imu           | sensor_msgs/Imu      | 100/200/300           |
| Intel RealSense T265  | /t265/image_left     | sensor_msgs/Image    | 30                    |
|                       | /t265/image_right    | sensor_msgs/Image    | 30                    |
|                       | /t265/imu            | sensor_msgs/Imu      | 65/200/265            |
| PiCam                 | /pi_cam_02/rgb_image | sensor_msgs/Image    | 30                    |
| VN100                 | /vn100/imu           | sensor_msgs/Imu      | 65                    |

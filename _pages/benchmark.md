---
title: Benchmark
author: Fabian Schmidt
date: 2024-10-31
category: Jekyll
layout: post
permalink: /pages/benchmark/
---
# Code
The code of the benchmark including utilities to support the dataset can be found on [https://github.com/iis-esslingen/rover_benchmark](https://github.com/iis-esslingen/rover_benchmark).
# Benchmark
We present the results of the experimental evaluation of the SLAM algorithms across a range of sensor configurations and environmental conditions.
## Location Specific Results
For each location, we report the Root Mean Square Error (RMSE) of the Absolute Trajectory Error (ATE) in meters, averaged over five runs. Invalid results are highlighted in red. An 'x' denotes that no trajectories were generated. 
### Park
![Park Results]({{ site.baseurl }}/assets/images/Park.png)

### Campus Small
![Campus Small Results]({{ site.baseurl }}/assets/images/Campus_Small.png)
### Campus Large
![Campus Large Results]({{ site.baseurl }}/assets/images/Campus_Large.png)

### Garden Small
![Garden Small Results]({{ site.baseurl }}/assets/images/Garden_Small.png)

### Garden Large
![Garden Large Results]({{ site.baseurl }}/assets/images/Garden_Large.png)

## Modality Comparison
Each modality was evaluated across all sequences to assess the impact of sensor configuration on SLAM performance. The results include comparisons between Monocular, Stereo, RGBD, and their inertial-enhanced counterparts, analyzing ATE and success rates to highlight strengths and weaknesses of each configuration.
Each cell presents the mean RMSE ATE (in meters) across the five locations – Park, Campus Small, Campus Large, Garden Small, and Garden Large. The second row in each cell shows the mean ATE across all locations, the standard deviation of the ATE, and the Success Rate in percent, calculated as the ratio of valid trajectories to the total number of trials for each configuration. The best and second best results for each location and the overall mean are highlighted in green.

### Mono
![Mono Results]({{ site.baseurl }}/assets/images/mono-results.png)

### Mono-Inertial
![Mono-Inertial Results]({{ site.baseurl }}/assets/images/mono-inertial-results.png)

### Stereo & Stereo-Inertial
![Stereo-Inertial Results]({{ site.baseurl }}/assets/images/stereo-stereo-inertial-results.png)

### RGBD & RGBD-Inertial
![RGBD-Inertial Results]({{ site.baseurl }}/assets/images/rgbd-rgbd-inertial-results.png)

## Environmental Robustness
The results of the best-performing sensor configuration of each SLAM method are shown in detail regarding different lighting conditions and seasonality. For each configuration, the mean ATE over five runs for the five locations is reported, along with the average across locations, the standard deviation, and the success rate. Best overall results are highlighted in green.

## Lighting Conditions
![Lighting Results]({{ site.baseurl }}/assets/images/lighting-results.png)

## Seasonality
![Season Results]({{ site.baseurl }}/assets/images/seasonality-results.png)

## Summary
![Summary Results]({{ site.baseurl }}/assets/images/summary_outcomes.png)

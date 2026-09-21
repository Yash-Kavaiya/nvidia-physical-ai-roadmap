# Phase 6 — Isaac ROS and Jetson

**Time:** 2–4 weeks

## Official path

- https://developer.nvidia.com/isaac/ros
- https://nvidia-isaac-ros.github.io/
- https://docs.nvidia.com/learning/physical-ai/getting-started-with-isaac-ros/latest/index.html
- https://nvidia-isaac-ros.github.io/repositories_and_packages/isaac_ros_physical_ai/index.html
- https://nvidia-isaac-ros.github.io/repositories_and_packages/isaac_ros_deploy/index.html

## Packages worth knowing

Visual SLAM, Nvblox, cuMotion, FoundationPose, NITROS, Isaac Manipulator, Isaac ROS Physical AI, Isaac ROS Deploy.

## Platform notes

- Newer humanoid / Thor workflows target **ROS 2 Jazzy** + JetPack 7.x
- Older Isaac ROS docs and many samples still assume **Humble** + JetPack 6.x on Orin
- Read the version matrix on the page you are following. Do not mix them.

## Project ladder

1. Dev container or venv from official docs
2. One GEM on a rosbag
3. SIL against Isaac Sim
4. HIL: policy on Jetson, scene on workstation
5. Optional real arm / G1 bringup

## Done when

A policy artifact from Phase 5 runs as a ROS 2 graph (sim is enough; hardware is better).

# Phase 5 — GR00T, VLAs, and sim-to-real

**Time:** 3–6 weeks

## Official path

- https://github.com/NVIDIA/Isaac-GR00T
- https://docs.nvidia.com/learning/physical-ai/index.html (G1 end-to-end course)
- https://docs.nvidia.com/learning/physical-ai/sim-to-real-so-101/latest/01-overview.html
- https://nvidia-isaac-ros.github.io/reference_workflows/isaac_for_physical_ai/index.html
- https://github.com/huggingface/lerobot
- https://github.com/NVlabs/GR00T-VisualSim2Real
- https://developer.nvidia.com/blog/building-generalist-humanoid-capabilities-with-nvidia-isaac-gr00t-n1-6-using-a-sim-to-real-workflow/

## Workflow to memorize

```text
Isaac Teleop / LeRobot demos
        -> Cosmos Transfer augmentation
        -> GR00T N post-train
        -> Isaac Lab-Arena eval
        -> LEAPP / ONNX export
        -> Isaac ROS Deploy
```

## Embodiment advice

- No hardware: Franka / UR / G1 in Isaac Sim only
- Low budget: SO-101 or Seeed reBot (NVIDIA has full courses)
- Research humanoid: Unitree G1 + Jetson Thor reference path

## Data quality rule

Fifty clean, varied demonstrations beat five hundred sloppy ones. GR00T will not invent a good grasp distribution you never showed it.

## Done when

A language-conditioned policy completes a pick or place task in sim (and on hardware if you have it), with notes on the remaining sim-to-real gap.

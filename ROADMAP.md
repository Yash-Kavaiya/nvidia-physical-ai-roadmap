# Full learning roadmap

Use this file as the long-form syllabus. Phase docs under `docs/phases/` are the working checklists.

## Phase 0 — Mental model (3–5 days)

**Goal:** Know which box does what. Do not install everything yet.

- Physical AI Learning hub: https://docs.nvidia.com/learning/physical-ai/index.html
- Cosmos product: https://www.nvidia.com/en-us/ai/cosmos/
- Humanoid three-computer solution: https://www.nvidia.com/en-us/use-cases/humanoid-robots/
- Blog: https://blogs.nvidia.com/blog/build-robots-with-ai/
- Blog: https://blogs.nvidia.com/blog/physical-ai-open-models-robot-autonomous-systems-omniverse/
- Jensen CES / GTC keynotes on Physical AI (NVIDIA On-Demand)

**Done when:** you can draw the three-computer loop and name Cosmos, Isaac Sim, Isaac Lab, GR00T, Isaac ROS, and Jetson without looking them up.

## Phase 1 — OpenUSD + Omniverse (1–2 weeks)

Physical AI scenes live in OpenUSD. Skip this and later tutorials become undebuggable magic.

- Learn OpenUSD: https://www.nvidia.com/en-us/learn/learning-path/openusd/
- Docs: https://docs.nvidia.com/learn-openusd/latest/index.html
- Agent Bootcamp: https://docs.nvidia.com/learning/physical-ai/physical-ai-agent-bootcamp/latest/index.html
- Omniverse hub: https://developer.nvidia.com/omniverse
- Warehouse SimReady assets: https://huggingface.co/datasets/nvidia/PhysicalAI-SimReady-Warehouse-01

**Practice:** assemble a warehouse scene; inspect prims, composition arcs, physics APIs, SimReady metadata.

**Optional:** OpenUSD Development Certification (NVIDIA DLI).

## Phase 2 — Isaac Sim (2–3 weeks)

**Goal:** import a robot, add sensors, run physics, talk to ROS 2, generate synthetic data.

- Learning path: https://docs.nvidia.com/learning/physical-ai/getting-started-with-isaac-sim/latest
- Docs: https://docs.isaacsim.omniverse.nvidia.com/latest/index.html
- Product: https://developer.nvidia.com/isaac/sim
- GitHub: https://github.com/isaac-sim/IsaacSim

**Projects in order**
1. First scene + Play/Stop + rigid bodies
2. Import a URDF (Franka, UR, SO-101, TurtleBot)
3. Add camera + lidar, save a Replicator dataset
4. ROS 2 bridge: drive the robot from a ROS node
5. Domain randomization for perception

## Phase 3 — Isaac Lab (2–4 weeks)

**Goal:** train a policy in thousands of parallel environments.

- Docs: https://isaac-sim.github.io/IsaacLab
- GitHub: https://github.com/isaac-sim/IsaacLab
- Product: https://developer.nvidia.com/isaac/lab

**Skills:** manager-based vs direct workflows; PPO / RSL-RL / SKRL / rl-games; imitation learning; domain randomization; Lab-Arena eval; ONNX / LEAPP export.

**First project ladder:** cartpole -> locomotion -> reach / lift on the manipulator from Phase 2.

## Phase 4 — Cosmos world models (2–3 weeks)

**Goal:** use world models as a data multiplier and physical reasoner.

- Quickstart: https://docs.nvidia.com/cosmos/latest/cosmos3/quickstart_guide.html
- GitHub: https://github.com/NVIDIA/cosmos
- Framework: https://github.com/nvidia/cosmos-framework
- Cookbook: https://nvidia-cosmos.github.io/cosmos-cookbook/
- Hugging Face: https://huggingface.co/collections/nvidia/cosmos3

**Model roles**
- **Predict** — future world states as video
- **Transfer** — spatially controlled visual augmentation
- **Reason** — VLM with physical common sense
- **Cosmos 3** — unified omnimodel (Nano / Super / Edge)
- **Curator** — GPU video filter / annotate / dedup

**Hands-on**
1. Cosmos Reason Q&A on a robot camera frame
2. One Isaac Sim clip -> Transfer -> dozens of visual variants
3. One cookbook recipe end-to-end
4. Optional LoRA / post-train on your domain

## Phase 5 — GR00T + VLA + sim-to-real (3–6 weeks)

**Goal:** post-train a robot brain and close the sim-to-real loop.

- GitHub: https://github.com/NVIDIA/Isaac-GR00T
- Hugging Face: `nvidia/GR00T-N1.7-3B`
- G1 course: Physical AI Learning hub
- SO-101 course: https://docs.nvidia.com/learning/physical-ai/sim-to-real-so-101/latest/01-overview.html
- Isaac for Physical AI: https://nvidia-isaac-ros.github.io/reference_workflows/isaac_for_physical_ai/index.html
- LeRobot: https://github.com/huggingface/lerobot
- Visual sim-to-real: https://github.com/NVlabs/GR00T-VisualSim2Real

**Master this workflow:** Teleop -> LeRobot dataset -> Cosmos augment -> GR00T post-train -> Lab-Arena -> LEAPP export -> Isaac ROS Deploy.

Affordable first embodiments: SO-101, Seeed reBot, or Franka / UR in sim only.

## Phase 6 — Isaac ROS + Jetson (2–4 weeks)

**Goal:** the policy leaves the workstation.

- Product: https://developer.nvidia.com/isaac/ros
- Docs: https://nvidia-isaac-ros.github.io/
- Packages: Visual SLAM, Nvblox, cuMotion, FoundationPose, NITROS, Isaac Manipulator, Isaac ROS Physical AI, Isaac ROS Deploy

**Projects**
1. Run one Isaac ROS GEM on recorded bags
2. SIL: Isaac Sim <-> Isaac ROS
3. HIL: workstation sim + Jetson inference
4. Deploy a reach / pick policy on a real arm if you have one

## Phase 7 — Specialize (ongoing)

See [`TRACKS.md`](TRACKS.md). Pick one track. Depth beats breadth.

## 90-day calendar

| Days | Outcome |
| --- | --- |
| 1–14 | OpenUSD + first Isaac Sim robot |
| 15–35 | Sensors, SDG, ROS 2 SIL |
| 36–55 | Isaac Lab trained policy + eval video |
| 56–75 | Cosmos pipeline + VLA / GR00T post-train |
| 76–90 | Export + deploy path + public write-up |

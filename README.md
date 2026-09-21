# NVIDIA Physical AI Roadmap

[![License: MIT](https://img.shields.io/badge/License-MIT-76B900.svg)](LICENSE)
[![Learning Path](https://img.shields.io/badge/path-beginner%20%E2%86%92%20production-76B900)](#90-day-plan)
[![Stack](https://img.shields.io/badge/stack-Cosmos%20%7C%20Isaac%20%7C%20Omniverse%20%7C%20GR00T-1A1A1A)](#ecosystem-map)
[![Maintainer](https://img.shields.io/badge/maintainer-Yash%20Kavaiya-blue)](https://github.com/Yash-Kavaiya)

> A complete, curated learning path for **NVIDIA Physical AI** — the stack that lets machines perceive, reason about, and act in the physical world.

This repository is a study guide, not an official NVIDIA product. It organizes official docs, courses, GitHub repos, Hugging Face models, and a 90-day plan so you can go from zero to a sim-to-real workflow.

**Start here**
1. Read the [ecosystem map](#ecosystem-map)
2. Check [prerequisites](#prerequisites)
3. Follow [phases 0–7](#learning-phases)
4. Pick a [specialization track](#specialization-tracks)
5. Track progress in [`LEARNING_LOG.md`](LEARNING_LOG.md)

---

## Why this repo exists

Physical AI is not one SDK. It is a **three-computer loop**:

| Computer | Role | Typical hardware |
| --- | --- | --- |
| **Train** | Foundation models, VLA post-training, world models | DGX / cloud GPUs |
| **Simulate** | Digital twins, synthetic data, policy training | Workstation + RTX / OVX |
| **Deploy** | Real-time perception and control | Jetson Thor / Orin on the robot |

NVIDIA’s current stack for that loop is **Cosmos + Omniverse/OpenUSD + Isaac Sim/Lab + GR00T + Isaac ROS + Jetson**. This repo is a map of that stack with working links.

---

## Ecosystem map

| Layer | What it does | Flagship products |
| --- | --- | --- |
| World models | Generate / reason about physical worlds, synthetic data, future states | **NVIDIA Cosmos** (Predict, Transfer, Reason, Cosmos 3 Nano / Super / Edge) |
| Simulation OS | Physically accurate 3D worlds and digital twins | **Omniverse libraries**, **OpenUSD**, PhysX / **Newton**, NuRec |
| Robot learning | Train policies at GPU scale (RL, imitation, VLA) | **Isaac Sim** + **Isaac Lab** |
| Robot brain | Vision-language-action models | **Isaac GR00T N** (N1.6 / N1.7) |
| AV brain | Reasoning models for driving | **Alpamayo** |
| Vision agents | Cameras, smart spaces, industrial perception | **Metropolis**, DeepStream, TAO |
| Runtime / edge | On-robot inference | **Jetson Thor / Orin**, **Isaac ROS** |
| Data factory | Teleop → synthetic scale-up → eval | Physical AI Data Factory Blueprint, OSMO, Cosmos Curator |
| Safety | Functional safety for uncaged robots | **Halos** |

The loop you should internalize:

```text
real / teleop demos
        |
        v
Cosmos Transfer / Predict  -- amplify rare cases
        |
        v
Isaac Lab / GR00T post-train
        |
        v
Isaac Lab-Arena + SIL eval
        |
        v
LEAPP / ONNX export
        |
        v
Isaac ROS on Jetson  -- real robot
        |
        +-------- more real data --> loop
```

---

## Prerequisites

You do **not** need a humanoid on day one.

**Skills**
- Python (intermediate): classes, virtualenvs / `uv`, scripts
- Linear algebra + basic 3D: frames, transforms, quaternions
- ML basics: PyTorch, training loops, transformers at a conceptual level
- Linux (Ubuntu 22.04 or 24.04) — Isaac Sim is happiest here
- Git + Hugging Face CLI

**Strongly recommended**
- ROS 2 concepts (nodes, topics, TF, `ros2_control`)
- Reinforcement learning intuition (PPO, imitation / DAgger)
- Basic 3D / CAD literacy (mesh, collider, joint)

**Hardware**

| Goal | Suggested hardware |
| --- | --- |
| Learn simulation | RTX 3070 / 4070 class, 16+ GB RAM, 250 GB free |
| Comfortable Isaac Sim / Lab | RTX 4080 / 5080 / professional GPU, 32–64 GB RAM, NVMe |
| Deploy a VLA / humanoid policy | Jetson AGX Thor (Orin is fine for smaller arms) |
| No local GPU | NVIDIA Brev / cloud Isaac Sim containers; Hugging Face Spaces for Cosmos inference |

Details: [`docs/01-prerequisites.md`](docs/01-prerequisites.md)

---

## Learning phases

| Phase | Focus | Time | Doc |
| --- | --- | --- | --- |
| 0 | Mental model of the stack | 3–5 days | [`docs/phases/00-mental-model.md`](docs/phases/00-mental-model.md) |
| 1 | OpenUSD + Omniverse | 1–2 weeks | [`docs/phases/01-openusd-omniverse.md`](docs/phases/01-openusd-omniverse.md) |
| 2 | Isaac Sim | 2–3 weeks | [`docs/phases/02-isaac-sim.md`](docs/phases/02-isaac-sim.md) |
| 3 | Isaac Lab | 2–4 weeks | [`docs/phases/03-isaac-lab.md`](docs/phases/03-isaac-lab.md) |
| 4 | Cosmos world models | 2–3 weeks | [`docs/phases/04-cosmos.md`](docs/phases/04-cosmos.md) |
| 5 | GR00T + VLA + sim-to-real | 3–6 weeks | [`docs/phases/05-groot-sim2real.md`](docs/phases/05-groot-sim2real.md) |
| 6 | Isaac ROS + Jetson | 2–4 weeks | [`docs/phases/06-isaac-ros-jetson.md`](docs/phases/06-isaac-ros-jetson.md) |
| 7 | Specialize | ongoing | [`docs/phases/07-specialize.md`](docs/phases/07-specialize.md) |

Full narrative roadmap: [`ROADMAP.md`](ROADMAP.md)

---

## 90-day plan

| Window | What to finish |
| --- | --- |
| Days 1–14 | OpenUSD modules + Agent Bootcamp start + Isaac Sim first robot |
| Days 15–35 | Sensors, Replicator SDG, ROS 2 SIL, import SO-101 or Franka |
| Days 36–55 | Isaac Lab reach / lift policy + Lab-Arena eval |
| Days 56–75 | Cosmos Reason + Transfer on your clips; GR00T or VLA post-train on LeRobot demos |
| Days 76–90 | Export policy, Isaac ROS Deploy in sim, optional Jetson HIL, write a public report |

Weekly mix that works: **60% hands-on / 20% docs / 20% papers and blogs**.

Copy [`LEARNING_LOG.md`](LEARNING_LOG.md) and tick boxes as you go.

---

## Specialization tracks

Pick **one** after Phase 5.

| Track | You will live in |
| --- | --- |
| Humanoids / loco-manipulation | GR00T N1.7, Isaac Lab Agile, Unitree G1, VIRAL / DoorMan, Jetson Thor |
| Industrial arms / factories | Isaac Manipulator, cuMotion, Mega / factory twins, SimReady warehouse USD |
| Autonomous vehicles | Alpamayo, Cosmos Transfer multiview, NuRec, AV Physical AI datasets |
| Vision AI / smart spaces | Metropolis, DeepStream, Cosmos Reason over cameras, TAO |
| Agent-driven Physical AI | NVIDIA skills + Physical AI Agent Bootcamp + Omniverse agent workflows |

See [`TRACKS.md`](TRACKS.md).

---

## Official learning catalog

| Resource | Level | URL |
| --- | --- | --- |
| Physical AI Learning hub | All | https://docs.nvidia.com/learning/physical-ai/index.html |
| Physical AI Agent Bootcamp | Beginner–intermediate | https://docs.nvidia.com/learning/physical-ai/physical-ai-agent-bootcamp/latest/index.html |
| Getting Started With Isaac Sim | Beginner | https://docs.nvidia.com/learning/physical-ai/getting-started-with-isaac-sim/latest |
| Getting Started With Isaac Lab | Intermediate | Physical AI hub |
| Getting Started With Isaac ROS | Intermediate | Physical AI hub |
| GR00T + Unitree G1 end-to-end | Intermediate | Physical AI hub |
| SO-101 sim-to-real | Intermediate | https://docs.nvidia.com/learning/physical-ai/sim-to-real-so-101/latest/01-overview.html |
| Learn OpenUSD | Beginner | https://www.nvidia.com/en-us/learn/learning-path/openusd/ |
| Cosmos Cookbook | Intermediate | https://nvidia-cosmos.github.io/cosmos-cookbook/ |
| Cosmos 3 quickstart | Intermediate | https://docs.nvidia.com/cosmos/latest/cosmos3/quickstart_guide.html |
| AI Learning Essentials | Intro | https://www.nvidia.com/en-us/learn/ai-learning-essentials/ |
| NVIDIA On-Demand / GTC | Mixed | Search “Physical AI”, “Isaac”, “Cosmos” |

Curated links: [`RESOURCES.md`](RESOURCES.md)

---

## Code, models, and datasets

**GitHub**
- https://github.com/NVIDIA/cosmos
- https://github.com/nvidia/cosmos-framework
- https://github.com/isaac-sim/IsaacSim
- https://github.com/isaac-sim/IsaacLab
- https://github.com/NVIDIA/Isaac-GR00T
- https://github.com/NVIDIA-ISAAC-ROS
- https://github.com/NVIDIA-Omniverse
- https://github.com/NVlabs/GR00T-VisualSim2Real
- https://github.com/huggingface/lerobot
- https://github.com/NVIDIA/skills

**Hugging Face**
- https://huggingface.co/collections/nvidia/physical-ai
- https://huggingface.co/collections/nvidia/cosmos3
- `nvidia/GR00T-N1.7-3B` and embodiment checkpoints
- `nvidia/PhysicalAI-SimReady-Warehouse-01`

Many Cosmos / GR00T weights are **gated**. Create a Hugging Face account and request access early.

---

## Common traps

1. One dirty conda env for Isaac Sim, Lab, Cosmos, and Isaac ROS. Use separate envs or official containers.
2. Skipping OpenUSD, then failing to debug asset / collider / scale bugs.
3. Five sloppy teleop demos and expecting GR00T to generalize.
4. Training only in pretty RTX mode and ignoring Lab’s tiled / headless parallel envs.
5. Buying a humanoid before you can deploy a 6-DoF arm policy.
6. Ignoring gated Hugging Face models until the night you need them.
7. Treating Cosmos as “a video generator.” It is a world model, reasoner, and data engine.

---

## Repo map

```text
nvidia-physical-ai-roadmap/
|-- README.md
|-- ROADMAP.md
|-- RESOURCES.md
|-- TRACKS.md
|-- LEARNING_LOG.md
|-- CONTRIBUTING.md
|-- LICENSE
`-- docs/
    |-- 01-prerequisites.md
    `-- phases/
        |-- 00-mental-model.md
        |-- 01-openusd-omniverse.md
        |-- 02-isaac-sim.md
        |-- 03-isaac-lab.md
        |-- 04-cosmos.md
        |-- 05-groot-sim2real.md
        |-- 06-isaac-ros-jetson.md
        `-- 07-specialize.md
```

---

## Suggested GitHub topics

```text
nvidia
physical-ai
robotics
isaac-sim
isaac-lab
isaac-ros
cosmos
omniverse
openusd
groot
jetson
humanoid-robots
sim-to-real
world-models
autonomous-vehicles
learning-path
```

Add them in the repo **About** panel — use the gear icon next to About on the repo homepage.

---

## Disclaimer

NVIDIA, Isaac, Omniverse, Cosmos, GR00T, Jetson, and related names are trademarks of NVIDIA Corporation. This repository is an independent learning guide. Links and version numbers change quickly; prefer official docs when they disagree with this repo.

---

## Maintainer

**Yash Kavaiya** — [GitHub](https://github.com/Yash-Kavaiya) · [X](https://x.com/yashkavaiya)

Contributions welcome. See [`CONTRIBUTING.md`](CONTRIBUTING.md).

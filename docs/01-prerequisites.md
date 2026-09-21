# Prerequisites

## Skills

| Skill | Why you need it |
| --- | --- |
| Python | Every NVIDIA sample, Isaac Lab task, and Cosmos script |
| 3D transforms | Robot bases, cameras, end-effectors, USD xforms |
| PyTorch literacy | Post-training GR00T / Cosmos and reading errors |
| Linux + CLI | Isaac Sim, Isaac ROS, JetPack |
| Git + Hugging Face CLI | Models are large and often gated |

ROS 2 and RL can be learned in parallel during Phases 2–3. Do not block Phase 0 on them.

## Software baseline

- Ubuntu 22.04 or 24.04 (x86_64)
- NVIDIA driver matching the Isaac Sim version you install
- `git`, `git-lfs`, `uv` or conda, Docker (recommended for Isaac ROS)
- Hugging Face account
- NGC account if you use NIM containers

## Hardware baseline

From NVIDIA’s Physical AI Agent Bootcamp guidance:

- 16 GB RAM minimum
- GeForce RTX 3070 or better
- ~250 GB free disk

Isaac Sim and Isaac Lab want more VRAM and system RAM as scenes grow. Jetson AGX Thor is the current on-robot target for GR00T-class models; Jetson Orin is still useful for smaller policies and Isaac ROS GEMs.

## Version pairing

Always install **Isaac Lab for the Isaac Sim version you have**. The Isaac Lab README publishes a compatibility table. Mixing versions is the most common first-week failure.

## Cloud option

If your laptop cannot run Isaac Sim:

- Isaac Sim containers / Brev-style cloud workstations
- Cosmos inference on a rented GPU
- Collect real-robot data later; do Phases 0–4 in the cloud first

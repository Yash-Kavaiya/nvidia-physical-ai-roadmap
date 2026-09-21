# Specialization tracks

Complete Phases 0–5 before locking a track. Switching later is expensive because each track has different data, robots, and safety constraints.

## A. Humanoids and loco-manipulation

**You build:** whole-body skills that transfer from Isaac Lab to a biped.

**Stack:** Isaac GR00T N1.7, Isaac Lab Agile locomotion, Isaac Teleop, Unitree G1 reference design, VIRAL / DoorMan, Bones-SEED motion data, Jetson Thor.

**Capstone ideas**
- G1 (or sim G1) pick-and-place from language command
- Door opening / loco-manipulation student policy
- Post-train GR00T on 100 high-quality bimanual demos

## B. Industrial arms and factories

**You build:** reliable pick, pack, inspect, or assemble cells.

**Stack:** Isaac Manipulator, cuMotion, Isaac Sim factory scenes, SimReady warehouse USD, Mega-style digital twins, Physical AI Data Factory Blueprint.

**Capstone ideas**
- Unstructured vial / SKU pick into a rack (SO-101 course pattern)
- Multi-object pick-and-place with FoundationPose + behavior trees
- Factory digital twin that generates training data for one cell

## C. Autonomous vehicles

**You build:** perception, world generation, or policy eval for driving.

**Stack:** Alpamayo, Cosmos Transfer multiview / HD map recipes, NuRec neural reconstruction, PhysicalAI-Autonomous-Vehicles datasets, DRIVE AGX conceptually.

**Capstone ideas**
- Transfer-augment a multi-camera driving clip
- Reconstruct a short route with NuRec and drop it into sim
- Closed-loop eval recipe for a driving VLA (even if only in sim)

## D. Vision AI and smart spaces

**You build:** camera agents that reason about physical scenes.

**Stack:** Metropolis, DeepStream, Cosmos Reason, TAO, Jetson edge deployment.

**Capstone ideas**
- Cosmos Reason incident reasoning on a warehouse camera
- Virtual fence / safety zone prototype in a digital twin
- Edge VLM on Jetson summarizing a live RTSP stream

## E. Agent-driven Physical AI

**You build:** coding agents that run bounded NVIDIA workflows.

**Stack:** NVIDIA skills, Physical AI Agent Bootcamp, Omniverse libraries, Patterned Prompt Method (Goal, Skills, Context, Done When).

**Capstone ideas**
- Agent that validates SimReady assets and writes a report
- Agent that generates an Isaac Sim pick scene from a spec
- Skill wrapper around one Cosmos cookbook recipe

## How to choose

| If you care about... | Pick |
| --- | --- |
| Walking robots and generalist brains | A |
| Shipping automation this year | B |
| Cars / trucks / robotaxis | C |
| Cameras and operations software | D |
| Tooling and developer experience | E |

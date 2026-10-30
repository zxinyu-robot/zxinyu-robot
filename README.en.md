# Hi, I'm Xinyu Zeng 👋

### Robotics & Spatial Intelligence · Reliable Autonomy · Multi-Agent Coordination · Sociotechnical Systems

[![Email](https://img.shields.io/badge/Email-zxiangsheng%40outlook.com-0A66C2?logo=microsoftoutlook)](mailto:zxiangsheng@outlook.com)

[中文](./README.md) | **English**

> **From autonomous robots to governed intelligent systems.**
>
> From the autonomous operation of robots, to the coordination and governance of intelligent systems in open environments.

---

## Vision｜佛科 · Fork

> **Fork · 佛科 — Make technology like a clear sound: reliable, and doing no harm.**

**In the way of Fork, build a trustworthy, interpretable, and rollback-able spatial runtime for robots.**

Fork means branching from existing systems, inheriting from them, and continuing to evolve. I work to decouple, encapsulate, and standardize capabilities from mature systems into reusable, replaceable, and composable independent modules; then, through explicit interface contracts, state lifecycles, and failure-recovery mechanisms, make capability invocation traceable, system operation auditable, and exceptions controllable and recoverable.

"佛科" (Fó Kē) is a Chinese homophone of Fork, carrying a technical belief: advance technology with prudence, hold reliability as the engineering bottom line, and hold "do no harm" as the technical principle.

The value of technology lies not only in expanding the boundaries of capability, but also in a clear understanding of operational boundaries, failure boundaries, and accountability boundaries — this is the promise of a spatial runtime that keeps robots safe, trustworthy, and sustainable.

## Engineering Background and Principles

I have a communications engineering background. My engineering practice spans AGVs, GPS-denied UAVs, and quadrupedal / bipedal robots, often facing complex operating environments such as weak networks, strong interference, and mixed indoor-outdoor settings. Grounded in real robot systems, I study how autonomous agents manage trustworthy state, behavior execution, and failure recovery under uncertainty, and further explore how these mechanisms extend to heterogeneous multi-agent coordination and to the governance of authority, risk, and accountability in human-robot shared environments.

- **Contract first**: validate any state before it enters the system — valid coordinates, legal ranges, matching versions; reject invalid input rather than propagate it.
- **Determinism**: bounded resources, reject rather than throw, ensuring predictable behavior on constrained real hardware.
- **Clear ownership**: single writer, read-only views; mutable state is never shared as raw pointers.
- **Verifiability**: simple control flow, testable states, and numbers that always carry their provenance (delivered / public prototype / research exploration).
- **Learned outputs are candidates, not commands**: only proposals, carrying confidence, version, and failure flags; final execution authority stays with the local controller.

---

## 🔧 What I'm Working On

**1. Reliable autonomous navigation**
Cross-floor goal navigation for quadrupedal robots; the real-robot loop is complete. The current focus is aligning localization state, task contracts, planning interfaces, and failure-recovery semantics: when localization degrades, planning fails, or execution times out, how does the system recognize the fault, take safe actions, and resume the task once recovery conditions are met?

**2. Reusable spatial runtime middleware**
A self-developed runtime for spatial state, task contracts, and execution lifecycles, so that the source, version, confidence, validity period, and failure semantics of state can be clearly understood by downstream planning and execution modules.

**3. Multi-robot coordination under weak networks**
A self-developed adaptive communication and versioned submap-fusion middleware for weak networks, studying how partial information, communication latency, and data inconsistency affect multi-robot coordination.

*Near-term goal*: turn these engineering problems into measurable research questions through real-robot experiments, data replay, controlled fault injection, and comparative evaluation.

---

## 🧩 Selected Projects

> All public repositories are buildable and testable; repos marked ▶ ship a runnable demo (terminal replay). Visual demos are being added progressively.

**▶ Demo Quick View (terminal replay)**

| Repository | Command | Shows |
|---|---|---|
| legged-navigation-runtime | `./build/default/recovery_demo` | localization loss → search → alignment → recovery |
| swarm-spatial-link | `./build/default/weak_link_demo` | adaptive QoS across three link states |
| fork-spatial-runtime | `./build/default/examples/cpp/runtime_demo` | graph transactions and state lifecycle |
| multi-robot-map-fusion | `./build/default/fusion_demo` | shared memory + submap registration |
| legged-terrain-state | `./build/default/terrain_demo` | terrain risk grading and safety modes |
| SlamDoctor-Runtime | `slam-doctor diagnose examples/nav_oscillation.jsonl` | root-cause triage of eight symptom classes |

Sample (legged-navigation-runtime, synthetic replay):

```text
$ ./build/default/recovery_demo
relocalization replay
  t= 100 ms  tracking -> tracking   action=hold_motion
  t= 600 ms  tracking -> searching   action=search_candidate
  t= 800 ms  searching -> aligning   action=run_fine_alignment
  t=1100 ms  aligning -> verifying   action=reset_localizer
  t=1400 ms  verifying -> tracking   action=resume_navigation
synthetic latency window: samples=10 p50=17.2 ms p95=24.8 ms max=24.8 ms
```

**End-side systems for three platforms** (one repository per platform)

| Platform | Repository | Current verification level | Demo |
|---|---|---|---|
| Unitree Go2 quadruped | quadruped-crossfloor-nav-ws | Cloud simulation cross-floor loop 11/11; real-robot online mapping and planning | ▶ [3D online demo](https://zxinyu-robot.github.io/musical-robot.github.io/dog/) |
| Unitree G1 / H2 biped | legged-navigation-runtime | Sanitized rewrite: localization recovery core + unit tests | ▶ recovery_demo |
| Compound cleaning robot (mobile base + xArm) | CleanRobot-Sim2Real-skill | MuJoCo simulation, not yet on real robots | — |

- **[quadruped-crossfloor-nav-ws](https://github.com/zxinyu-robot/quadruped-crossfloor-nav-ws)** — An end-side autonomous navigation loop for Go2 + Livox Mid-360 + Orin NX (ROS 2, cross-floor). Behavior-tree orchestration, task runtime, and command forwarding are self-developed; localization (Super-LIO) and global / local planning (PCT / SCAN) are engineering integrations on open-source components. The cross-floor loop has been completed in cloud simulation (multi-floor tasks 11/11 success), and online mapping and planning have run on the real robot; it is being integrated with ForkSpatial-Runtime-Engine's state contracts and legged-navigation-runtime's recovery plugin for end-to-end drills with fault injection.
- **[legged-navigation-runtime](https://github.com/zxinyu-robot/legged-navigation-runtime)** — A sanitized rewrite of the G1 / H2 biped end-side autonomous navigation loop, exposing the localization failure recovery part: localization health and relocalization state machine (Tracking → Searching → Aligning → Verifying → SafeStop), registration gating, timeout protection, and P50 / P95 latency statistics. The core has no ROS dependency; `RecoveryPlugin` is integrated into quadruped-crossfloor-nav-ws, so bipeds and quadrupeds share the same recovery logic.
- **[CleanRobot-Sim2Real-skill](https://github.com/zxinyu-robot/CleanRobot-Sim2Real-skill)** — The skill layer of a compound cleaning robot. The original project is a ROS1 real-robot system (xArm, RealSense, mobile base, cleaning actuators); this repository implements tool pick-and-place and surface cleaning, an independent safety layer, and a bounded residual policy in MuJoCo, not yet deployed on real robots.

**Cross-platform spatial runtime**

- **[ForkSpatial-Runtime-Engine](https://github.com/zxinyu-robot/ForkSpatial-Runtime-Engine)** — A C++20 spatial state runtime: state contracts (version chains, localization health, execution leases, admission checks, fault injection), semantic tokens, ESN temporal memory, and end-side policy management (candidate policies verified before publishing, rollback-able) and task orchestration. Weak-network transport scheduling and DDS protocol generation are not yet implemented.

**Localization safety & diagnostics** (division of labor: sensor-layer isolation / runtime recovery / post-hoc diagnosis)

- **[SensorGuardNav-Runtime](https://github.com/zxinyu-robot/SensorGuardNav-Runtime)** — Localization self-rescue when LiDAR is polluted: detection, confidence arbitration, a seven-state state machine, safe speed caps, and recovery gating; implemented in Python with fault injection and JSONL replay, currently validated only on synthetic data.
- **[SlamDoctor-Runtime](https://github.com/zxinyu-robot/SlamDoctor-Runtime)** — A SLAM / navigation diagnostics CLI: checks time, coordinate, frequency, and data-age contracts; ranks root causes via a fault graph and suggests the next low-cost probe; outputs JSON / Markdown / Mermaid reports.
- **[legged-terrain-state](https://github.com/zxinyu-robot/legged-terrain-state)** — State contracts and safe degradation for quadrupedal mixed-terrain navigation: traversability scoring, risk grading, and Normal / ReduceSpeed / HoldPosition safety modes.

**Multi-robot infrastructure**

- **[swarm-spatial-link](https://github.com/zxinyu-robot/swarm-spatial-link)** — A sanitized rewrite of a multi-robot cooperative SLAM project: classifies links into Healthy / Constrained / Critical based on loss / latency / queue, applies different DDS QoS to pose, keyframe, and submap topics; also includes clock-offset estimation and keyframe scheduling.
- **[multi-robot-map-fusion](https://github.com/zxinyu-robot/multi-robot-map-fusion)** — A POSIX shared-memory keyframe channel (`shm_open` + `mmap`, sequence numbers and checksums) and a versioned submap registry (idempotent reception, constraint validation, `graph_version` increments).

**Learning baselines**

- **[interactive-nav-learning](https://github.com/zxinyu-robot/interactive-nav-learning)** — An interruptible navigation learning baseline: behavior cloning, DAgger, and mid-trajectory language correction in a 2D environment, reproducible on CPU.
- **[terrain-carry-rl](https://github.com/zxinyu-robot/terrain-carry-rl)** — An integrated RL scaffold for Go2 + Piper manipulator: 19-DoF actions, teacher→student distillation, domain randomization, and latency modeling; not yet connected to Isaac Lab, no training results yet.

> Repositories marked "sanitized rewrite" are public rewrites of past engineering work, containing only independently testable cores; complete systems, vendor SDKs, and real-robot data are not public. Implementation status is subject to each repository's code, tests, and documentation.

---

## Methodology: Spatial Map Foundation and the Three-Space Framework

**The map is the metric foundation of navigation.** Its core abstraction has only three layers:

- **Coordinate contract** — a global absolute reference (e.g., WGS84 lat / lon / alt), so any local result can be traced back to a verifiable geographic ground truth;
- **Tile partitioning** — bounded spatial regions with stable identifiers; local maps (SLAM's map / odom) align to a global tile reference, forming a layered map that is "locally updatable, globally addressable";
- **Hash addressing** — tiles are addressed by a uniform scheme (e.g., Amap / XYZ tile hashing), so a city-scale, cross-machine, cross-vendor spatial index can be shared.

This forms an evolutionary path: **local robot metric maps → city-scale tiled maps → persistent metaverse spatial maps**.

On this foundation, autonomy and coordination both reduce to exchanging three spaces under consistent time, coordinate frames, and versions — rather than conflating them inside a single large model:

| Space | What it carries | Corresponding chain |
| --- | --- | --- |
| metric space | pose, map, trajectory, covariance | state chain |
| symbolic space | semantics, skills, tasks, preconditions | task chain |
| world space | prediction, decision, state evolution | prediction chain |

---

## 🧠 Research Agenda

These questions emerged gradually from engineering practice and are still evolving. I treat my current system designs and learning mechanisms as hypotheses to be tested, not final answers. The research proceeds through three progressive layers.

### Layer 1 · Autonomous Systems

How to manage spatial state, task contracts, behavior execution, and failure recovery so that autonomous systems are verifiable and recoverable.

**01 — State Reliability**
How should autonomous systems represent, validate and manage the lifecycle of spatial and decision-relevant states?

*Mapping*: how local map / odom alignment to the global tile reference keeps coordinates, versions, and confidence verifiable (metric space).

**02 — Experience and Adaptive Behavior**
How can robots accumulate reusable behavioral experience without blindly reusing outdated or context-inappropriate policies?

*Mapping*: how episodic / temporal memory expires when map versions expire (world space).

*Verification paths*: stale-state detection, relocalization success rate, recovery time, safe stop, task completion rate.

### Layer 2 · Multi-Agent Coordination

How to achieve multi-agent coordination, task allocation, and risk control under heterogeneous capabilities, partial information, communication constraints, and dynamic environments.

**03 — Resilient Multi-Agent Coordination**
How can heterogeneous agents coordinate and recover under partial observability, limited communication and conflicting constraints?

*Mapping*: map consistency and version conflicts when multiple agents share the same tile-addressed space (metric + symbolic space).

*Verification paths*: coordination performance under loss and latency, communication overhead, map consistency, task recovery capability.

### Layer 3 · Sociotechnical Systems

When autonomous agents enter public spaces, production systems, and urban infrastructure, how to design coordination rules, responsibility boundaries, and risk governance mechanisms.

**04 — Authority and Accountability**
How should task authority, human intervention, escalation rules and accountability be distributed among autonomous agents, operators and institutions in shared environments?

*Mapping*: sharing rules, authority, and accountability for city-scale persistent spatial maps, toward a metaverse spatial map (symbolic space).

*Exploration paths*: human intervention rules, task authorization, escalation workflows, traceability of decisions and responsibilities.

---

## 🧭 Research Approach

- **Systems engineering** — define contracts for state, task, authority, and failure recovery; the map is organized in three layers: coordinate contract, tile partitioning, and hash addressing.
- **Computational experiments** — real robots, data replay, controlled fault injection, and comparative experiments.
- **Candidate mechanisms** — semantic state tokens, temporal / episodic memory (e.g., ESN), end-side continual adaptation, world models; each evaluated independently and replaceable, rather than a predetermined single path.
- **Sociotechnical analysis** (planned) — combining STS, Technology Policy, and Computational Social Science to analyze how role division, operating rules, human intervention, and accountability mechanisms shape the actual operation of intelligent systems.

---

## Contact

佛科 (Fork) is currently initiated and maintained by me personally; partners who share this vision and wish to build it together over the long term are welcome to join.

**My guiding question:**

*How can we build autonomous intelligent systems that are not only capable of acting, but also reliable in execution, accountable in operation, and compatible with the societies they serve?*

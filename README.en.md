# Hi, I'm Xinyu Zeng 👋

### Robotics & Spatial Intelligence · Reliable Autonomy · Multi-Agent Coordination · Sociotechnical Systems

[![Email](https://img.shields.io/badge/Email-zxiangsheng%40outlook.com-0A66C2?logo=microsoftoutlook)](mailto:zxiangsheng@outlook.com)

[中文](./README.md) | **English**

## About Me

> **From Engineering Practice to Systems Thinking**
>
> Coming from communications engineering, I have been developing autonomous systems for unmanned systems and robots, covering autonomous navigation, embedded systems, and middleware in GPS-denied, weak-network, and dynamic environments.
>
> As my practice extended from low-level state estimation and system implementation to the interaction between spatial state and upstream agents, my focus shifted from individual algorithms to the organizational mechanisms of intelligent systems: **how to understand and manage spatial state, organize intelligent behavior, and enable different agents to coordinate reliably under uncertainty.**

---

## Engineering Capabilities

Organized as complete engineering-chain capabilities, not a tech-stack list:

| Capability | Contents |
| --- | --- |
| Autonomous robot systems | SLAM, navigation, planning & control, behavior orchestration, fault recovery |
| Middleware & system architecture | Messaging, DDS, task lifecycle, state management, multi-robot coordination |
| Embedded & edge-cloud | Linux, C++, embedded deployment, edge resource scheduling, system integration |
| Spatial intelligence & interaction | Multi-space state representation, world-state distribution, model-robot async interaction |

---

## Selected Engineering Work

Three representative work stages; commercial work, production work, and personal open-source rewrites are stated separately.

### Case A · Autonomous robot systems in constrained environments

- **Background**: UAV and multi-robot navigation in GPS-denied, weak-network, industrial-inspection environments.
- **Role**: Autonomous navigation R&D, state-machine task orchestration, multi-robot coordination, embedded deployment and integration.
- **Approach**: Built a GPS-denied UAV navigation task-execution middleware product on message-oriented middleware, on geometric SLAM and classical motion control; participated in military aircraft navigation module R&D.
- **Outcome**: Delivered across AGV, GPS-denied quadrotor, quadrupedal and bipedal platforms in weak-network, strong-interference, mixed indoor-outdoor environments.

**▶ Demo (click cover to play)**

| Military aircraft navigation module (sanitized simulator showcase) | GPS-denied UAV autonomous inspection in darkness |
| --- | --- |
| [![Military aircraft navigation module](assets/demo/uav_gps_denied_15s_cover.png)](assets/demo/uav_gps_denied_15s.mp4) | [![Autonomous inspection in darkness](assets/demo/uav_dark_patrol_cover.png)](assets/demo/uav_dark_patrol.mp4) |

### Case B · Legged robot autonomous navigation in dynamic environments

- **Background**: Long-duration, cross-floor goal navigation for quadrupedal robots in dynamic, unstructured environments.
- **Role**: Edge-cloud resource allocation, self-developed navigation middleware, scenario adaptation of key algorithms.
- **Approach**: Built edge-cloud navigation middleware, unifying localization state, task contracts, planning interfaces, and fault-recovery semantics.
- **Outcome**: Cross-floor loop passed cloud simulation 11/11; real-robot online mapping and planning running (see [quadruped-crossfloor-nav-ws](https://github.com/zxinyu-robot/quadruped-crossfloor-nav-ws)).

**▶ Demo**

| Quadruped cross-floor navigation | SLAM visualization | Point-cloud mapping |
| --- | --- | --- |
| <img src="https://raw.githubusercontent.com/zxinyu-robot/quadruped-crossfloor-nav-ws/main/docs/media/cross_floor_demo.webp" width="400"> | <img src="assets/demo/img_v3_0214n_cc9e8535-cba3-4ea1-aeb3-80fbb87d9afg.jpg" width="400"> | <img src="assets/demo/54.jpg" width="400"> |

### Case C · Spatial state and intelligent system interaction

- **Background**: How robot spatial state can be reliably consumed by upstream agents and world models.
- **Role**: Engineering the three-space framework; designing world-state data distribution.
- **Approach**: Built a data-distribution middleware for the world-space state produced by legged robots, enabling asynchronous state-task navigation behavior interaction with upstream world models.
- **Outcome**: Publicly rewritten into buildable, testable cores — state contracts, localization recovery, terrain contracts, weak-network coordination, shared-memory fusion, read-only diagnostics.

**▶ Demo (localization recovery state machine)**

<img src="https://raw.githubusercontent.com/zxinyu-robot/quadruped-crossfloor-nav-ws/main/docs/media/state_flow_seq.png" width="560">

---

## Current Focus

Unified direction: **autonomous intelligent systems in real environments, and their organization**.

Three research scales (progressive):

1. **Single-agent intelligence** — spatial state understanding, autonomous behavior, long-horizon task execution, fault recovery;
2. **Multi-agent intelligence** — heterogeneous robots, coordination, information sharing, task organization;
3. **Sociotechnical systems** — human-robot collaboration, authority allocation, risk governance, accountability.

Recent work:

- **Reliable autonomous navigation**: the real-robot cross-floor navigation loop is complete; current focus is aligning localization state, task contracts, planning interfaces, and failure-recovery semantics.
- **Reusable spatial runtime middleware**: making state's source, version, confidence, validity, and failure semantics explicit to downstream modules.
- **Multi-robot coordination under weak networks**: adaptive communication and versioned submap fusion; how partial information and inconsistency affect coordination.

---

## Fork · Engineering Philosophy

Fork is not a technology route competing with existing systems, but a set of **engineering values** formed through long-term practice.

- **Technology should serve real problems** — not technology for its own sake, not complexity as a measure of value.
- **Autonomy is not the absence of constraints** — intelligent systems should know their state, capability bounds, and behavioral authority.
- **Reliability comes from understandability and correctability** — explain state, recognize anomalies, recover, and allow rollback when needed.
- **Technological progress should respect human interests** — automation is not an excuse to evade responsibility; efficiency does not outrank safety.

> **佛科 · Fork — Technology should be reliable, and do no harm.**
>
> Fork means deriving capabilities from existing systems — through decomposition, composition, replacement, and evolution — to make technology interpretable, verifiable, and rollback-able.
>
> Engineering principles: **interpretable · verifiable · replaceable · rollback-able · reliable without harm**

---

## How I Think About Systems

### Three Spaces: how I understand the world a robot lives in

| Space | Question answered | Description |
| --- | --- | --- |
| Metric Space | Where am I? What is around me? Can I pass? | Localization, maps, geometric relations, motion state |
| Symbolic Space | What are the objects? What relations? What does the task mean? | Semantics, relations, constraints, task meaning |
| World Space | What state does the system believe the world is in? What is trusted, what can be executed? | Task-relevant state shared among the autonomous system, upstream agents, and world models |

The three spaces are an evolving systems-thinking framework — not three mutually exclusive map algorithms, and World Space is not conflated with World Model.

### State Contracts: how I understand system reliability

State is more than a data structure:

- **Source & time** — where and when it was produced;
- **Frame & version** — which spatial reference and version it belongs to;
- **Confidence & validity** — whether it is trusted, whether it has expired;
- **Lifecycle** — how it updates, expires, and is revoked;
- **Authority & accountability** — who may use, modify, and act on it.

This extends to task contracts, behavior execution, fault recovery, and multi-agent coordination.

### Research scales: what I want to keep answering

Single-agent intelligence → multi-agent systems → sociotechnical systems (see Research Agenda).

---

## Research Agenda

These questions emerged gradually from engineering practice and are still evolving. I treat my current designs and learning mechanisms as hypotheses to be tested, not final answers.

### Layer 1 · Autonomous Systems

How to manage spatial state, task contracts, behavior execution, and fault recovery so that autonomous systems are verifiable and recoverable.

**01 — State Reliability**
How should autonomous systems represent, validate and manage the lifecycle of spatial and decision-relevant states?

**02 — Experience and Adaptive Behavior**
How can robots accumulate reusable behavioral experience without blindly reusing outdated or context-inappropriate policies?

*Verification paths*: stale-state detection, relocalization success rate, recovery time, safe stop, task completion rate.

### Layer 2 · Multi-Agent Coordination

How to achieve multi-agent coordination, task allocation, and risk control under heterogeneous capabilities, partial information, communication constraints, and dynamic environments.

**03 — Resilient Multi-Agent Coordination**
How can heterogeneous agents coordinate and recover under partial observability, limited communication and conflicting constraints?

*Verification paths*: coordination under loss and latency, communication overhead, map consistency, task recovery.

### Layer 3 · Sociotechnical Systems

When autonomous agents enter public spaces, production systems, and urban infrastructure, how to design coordination rules, responsibility boundaries, and risk governance.

**04 — Authority and Accountability**
How should task authority, human intervention, escalation rules and accountability be distributed among autonomous agents, operators and institutions in shared environments?

*Exploration paths*: human intervention rules, task authorization, escalation workflows, traceability of decisions and responsibilities.

### Research Approach

- **Systems engineering** — define contracts for state, task, authority, and failure recovery.
- **Computational experiments** — real robots, data replay, controlled fault injection, comparative evaluation.
- **Candidate mechanisms** — semantic state tokens, temporal / episodic memory, end-side continual adaptation, world models; each evaluated independently and replaceable.
- **Sociotechnical analysis** (planned) — combining STS, Technology Policy, and Computational Social Science.

---

## Open Source Projects

> All public repositories are buildable and testable; repos marked ▶ ship a runnable demo. Commercial and production systems are not public — only independently testable core rewrites are listed.

**▶ Demo Quick View (terminal replay)**

| Repository | Command | Shows |
| --- | --- | --- |
| legged-navigation-runtime | `./build/default/recovery_demo` | localization loss → search → alignment → recovery |
| swarm-spatial-link | `./build/default/weak_link_demo` | adaptive QoS across three link states |
| fork-spatial-runtime | `./build/default/examples/cpp/runtime_demo` | graph transactions and state lifecycle |
| multi-robot-map-fusion | `./build/default/fusion_demo` | shared memory + submap registration |
| legged-terrain-state | `./build/default/terrain_demo` | terrain risk grading and safety modes |
| SlamDoctor-Runtime | `slam-doctor diagnose examples/nav_oscillation.jsonl` | root-cause triage of eight symptom classes |

**End-side systems for three platforms**

| Platform | Repository | Current verification level | Demo |
| --- | --- | --- | --- |
| Unitree Go2 quadruped | quadruped-crossfloor-nav-ws | Cloud sim cross-floor 11/11; real-robot online mapping & planning | ▶ video in repo `docs/media/` |
| Unitree G1 / H2 biped | legged-navigation-runtime | Sanitized rewrite: recovery core + unit tests | ▶ recovery_demo |
| Compound cleaning robot | CleanRobot-Sim2Real-skill | MuJoCo simulation, not on real robots | — |

**Cross-platform spatial runtime**

- [ForkSpatial-Runtime-Engine](https://github.com/zxinyu-robot/ForkSpatial-Runtime-Engine) — C++20 spatial state runtime: state contracts, semantic tokens, ESN temporal memory, end-side policy management, task orchestration.

**Localization safety & diagnostics**

- [SensorGuardNav-Runtime](https://github.com/zxinyu-robot/SensorGuardNav-Runtime) — localization self-rescue under LiDAR pollution: detection, confidence arbitration, seven-state machine, safe speed caps, recovery gating.
- [SlamDoctor-Runtime](https://github.com/zxinyu-robot/SlamDoctor-Runtime) — SLAM/navigation diagnostics CLI: contract checks, fault-graph root-cause ranking, next low-cost probe; JSON/Markdown/Mermaid output.
- [legged-terrain-state](https://github.com/zxinyu-robot/legged-terrain-state) — quadruped mixed-terrain state contracts and safe degradation: traversability scoring, risk grading, Normal/ReduceSpeed/HoldPosition.

**Multi-robot infrastructure**

- [swarm-spatial-link](https://github.com/zxinyu-robot/swarm-spatial-link) — weak-network adaptive communication: Healthy/Constrained/Critical QoS, clock-offset estimation, keyframe scheduling.
- [multi-robot-map-fusion](https://github.com/zxinyu-robot/multi-robot-map-fusion) — POSIX shared-memory keyframe channel and versioned submap registry (idempotent reception, constraint validation, graph_version increments).

**Learning baselines**

- [interactive-nav-learning](https://github.com/zxinyu-robot/interactive-nav-learning) — interruptible navigation learning: behavior cloning, DAgger, mid-trajectory language correction.
- [terrain-carry-rl](https://github.com/zxinyu-robot/terrain-carry-rl) — Go2 + Piper integrated RL scaffold: 19-DoF actions, teacher→student distillation, domain randomization, latency modeling.

> Repositories marked "sanitized rewrite" are public rewrites of past engineering work, containing only independently testable cores; complete systems, vendor SDKs, and real-robot data are not public. Status is subject to each repository's code, tests, and docs.

---

## Contact

佛科 (Fork) is currently initiated and maintained by me personally; partners who share these values and wish to build together over the long term are welcome.

**My guiding question:**

*How can we build autonomous intelligent systems that are not only capable of acting, but also reliable in execution, accountable in operation, and compatible with the societies they serve?*

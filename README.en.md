<div align="center">

# Hi, I'm Xinyu Zeng（曾欣宇）👋

### Robotics & Spatial Intelligence · Reliable Autonomy · Multi-Agent Coordination · Sociotechnical Systems

[![Email](https://img.shields.io/badge/Email-zxiangsheng%40outlook.com-0A66C2?logo=microsoftoutlook)](mailto:zxiangsheng@outlook.com)

[中文](./README.md) | **English**

</div>

> **From autonomous robots to governed intelligent systems.**

Building on real robot systems, I study how autonomous agents organize trustworthy state and manage execution and failure recovery in uncertain environments, and how these mechanisms extend to heterogeneous multi-agent coordination and to authority, risk and accountability in shared human–machine environments.

My background is in communications. My engineering work covers AGVs, GPS-denied quadrotors and quadruped / biped robots, in weak-network, GPS-denied, high-interference and mixed indoor–outdoor scenarios.

---

## 🔧 What I'm Working On

**1. Reliable Autonomous Navigation**
Cross-floor navigation now runs end-to-end on a real quadruped. Current work aligns localization state, task contracts, planning interfaces and recovery semantics: when localization degrades, planning fails or execution times out, how does the system detect the fault, act safely, and resume once recovery conditions are met?

**2. Reusable Spatial Runtime**
A self-developed runtime for spatial state, task contracts and execution lifecycle, making the source, version, confidence, validity and failure semantics of state explicit to downstream planning and execution.

**3. Multi-Robot Coordination under Weak Connectivity**
Self-developed middleware for weak-network adaptive communication and versioned submap fusion, studying how partial information, latency and inconsistency affect multi-robot coordination.

*Immediate goal:* turn these engineering problems into measurable research questions through real-robot experiments, replay, controlled failure injection and comparative evaluation.

## 🧩 Selected Projects

**Autonomous Runtime**
- **[MotionSLAM_ws](https://github.com/zxinyu-robot/MotionSLAM_ws)** — Quadruped navigation stack; cross-floor navigation validated on a real robot.
- **[legged-navigation-runtime](https://github.com/zxinyu-robot/legged-navigation-runtime)** — Fault-tolerant navigation runtime: from one-off planning success to sustained operation with explicit fault boundaries and recovery conditions.
- **[fork-spatial-runtime](https://github.com/zxinyu-robot/fork-spatial-runtime)** — Reusable runtime for spatial state, task contracts and execution lifecycle.

**Multi-Robot Infrastructure**
- **[swarm-spatial-link](https://github.com/zxinyu-robot/swarm-spatial-link) · [multi-robot-map-fusion](https://github.com/zxinyu-robot/multi-robot-map-fusion)** — Self-developed middleware cores: weak-network adaptive communication; shared-memory data path with versioned submap fusion.

**Tools & Baselines**
- **[SlamDoctor](https://github.com/zxinyu-robot/SlamDoctor)** — Self-developed SLAM / navigation diagnosis CLI based on runtime evidence and fault graphs.
- [legged-terrain-state](https://github.com/zxinyu-robot/legged-terrain-state) · [interactive-nav-learning](https://github.com/zxinyu-robot/interactive-nav-learning)

---

## 🧠 Research Agenda

These questions grew out of engineering practice and are still evolving. I treat the current system designs and learning mechanisms as hypotheses to be tested, not final answers. The agenda has three progressive layers.

### Layer 1 · Autonomous Systems

How to manage spatial state, task contracts, behavior execution and failure recovery so that autonomous systems operate verifiably and recoverably.

**01 — State Reliability**

How should autonomous systems represent, validate and manage the lifecycle of spatial and decision-relevant states?

**02 — Experience and Adaptive Behavior**

How can robots accumulate reusable behavioral experience without blindly reusing outdated or context-inappropriate policies?

*Validation:* stale-state detection, relocalization success rate, recovery time, safe stops, task completion rate.

### Layer 2 · Multi-Agent Coordination

How to achieve coordination, task allocation and risk control under heterogeneous capabilities, partial information, communication constraints and dynamic environments.

**03 — Resilient Multi-Agent Coordination**

How can heterogeneous agents coordinate and recover under partial observability, limited communication and conflicting constraints?

*Validation:* coordination under packet loss and latency, communication overhead, map consistency, task recovery.

### Layer 3 · Sociotechnical Systems

As autonomous agents enter public spaces, production systems and urban infrastructure, how should coordination rules, responsibility boundaries and risk governance be designed?

**04 — Authority and Accountability**

How should task authority, human intervention, escalation rules and accountability be distributed among autonomous agents, operators and institutions in shared environments?

*Exploration:* human-intervention rules, task authorization, fault escalation procedures, traceability of decisions and responsibility.

## 🧭 Research Approach

- **Systems engineering** — define contracts for state, tasks, authority and failure recovery.
- **Computational experiments** — real robots, data replay, controlled failure injection and comparative experiments.
- **Candidate mechanisms** — semantic state tokens, temporal / episodic memory (e.g. ESN), on-device continual adaptation, world models; each evaluated independently and replaceable, not a single predetermined route.
- **Sociotechnical analysis** (planned) — drawing on STS, Technology Policy and Computational Social Science to analyze how role division, operating rules, human intervention and accountability mechanisms shape how intelligent systems actually run.

---

**Open to discussion**

**My guiding question:**

*How can we build autonomous intelligent systems that are not only capable of acting, but also reliable in execution, accountable in operation, and compatible with the societies they serve?*

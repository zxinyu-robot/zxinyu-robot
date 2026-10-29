<div align="center">

# Hi, I'm Xinyu Zeng（曾欣宇）👋

### Robotics & Spatial Intelligence · Reliable Autonomy · Multi-Agent Coordination · Sociotechnical Systems

[![Email](https://img.shields.io/badge/Email-zxiangsheng%40outlook.com-0A66C2?logo=microsoftoutlook)](mailto:zxiangsheng@outlook.com)

**中文** | [English](./README.en.md)

</div>

> **From autonomous robots to governed intelligent systems.**
>
> 从机器人的自主运行，到开放环境中智能系统的协同与治理。

我以真实机器人系统为工程基础，研究自主智能体在不确定环境中如何组织可信状态、管理行为执行与故障恢复，并进一步探索这些机制如何扩展到异构多智能体协同，以及人机共享环境中的权限、风险与责任治理。

我是通信背景，过往工程覆盖两个方面：一是平台，包括 AGV、无 GPS 四旋翼、四足 / 双足机器人；二是场景，包括弱网、无 GPS、强干扰与室内外混合环境。

---

## 🔧 What I'm Working On

**1. 可靠自主导航**
四足机器人跨楼层目标导航；
真机已完成闭环。当前重点是对齐定位状态、任务契约、规划接口与故障恢复语义：回答当定位退化、规划失败或执行超时时，系统如何识别故障、采取安全动作，并在满足恢复条件后继续执行任务？

**2. 可复用空间运行时中间件系统**
*自研空间状态、任务契约与执行生命周期的运行时，让状态的来源、版本、置信度、有效期和失败语义能被下游规划与执行模块明确理解。

**3. 弱网下的多机协同**
*自研面向弱网的自适应通信与版本化子图融合中间件，研究局部信息、通信延迟和数据不一致如何影响多机器人协同。

*近期目标*：
*通过真机实验、数据回放、可控故障注入与对照评估，把这些工程问题转化为可度量的研究问题。

## 🧩 Selected Projects

**三个平台的端侧系统**（每个平台对应一个仓库）

| 平台 | 仓库 | 当前验证程度 |
|---|---|---|
| Unitree Go2 四足 | quadruped-crossfloor-nav-ws | 云端仿真跨楼层闭环 11/11；真机在线建图与规划 |
| Unitree G1 / H2 双足 | legged-navigation-runtime | 脱敏重构：定位恢复核心 + 单元测试 |
| 复合清洁机器人（移动底盘 + xArm） | CleanRobot-Sim2Real-skill | MuJoCo 仿真，尚未上真机 |

- **[quadruped-crossfloor-nav-ws](https://github.com/zxinyu-robot/quadruped-crossfloor-nav-ws)** — Go2 + Livox Mid-360 + Orin NX 的端侧自主导航闭环（ROS 2，跨楼层）。行为树编排、任务运行时和指令转发为自研；定位（Super-LIO）、全局 / 局部规划（PCT / SCAN）在开源组件上做工程集成。跨楼层闭环已在云端仿真中跑通（多楼层任务 11/11 成功），真机上在线建图与规划已运行；正在接入 ForkSpatial-Runtime-Engine 的状态契约与 legged-navigation-runtime 的恢复插件，用故障注入做端到端演练。
- **[legged-navigation-runtime](https://github.com/zxinyu-robot/legged-navigation-runtime)** — G1 / H2 双足端侧自主导航闭环的脱敏重构，公开的是定位失效恢复部分：定位健康度与重定位状态机（Tracking → Searching → Aligning → Verifying → SafeStop）、配准门控、超时保护和 P50 / P95 延迟统计。核心无 ROS 依赖；`RecoveryPlugin` 已作为恢复插件接入 quadruped-crossfloor-nav-ws，双足、四足共用同一套恢复逻辑。
- **[CleanRobot-Sim2Real-skill](https://github.com/zxinyu-robot/CleanRobot-Sim2Real-skill)** — 复合清洁机器人的操作技能层。原工程是 ROS1 真机系统（xArm、RealSense、移动底盘、清洁执行器）；本仓库在 MuJoCo 中实现工具拾放与表面清洁、独立安全层和有界残差策略，尚未上真机。

**跨平台空间运行时**
- **[ForkSpatial-Runtime-Engine](https://github.com/zxinyu-robot/ForkSpatial-Runtime-Engine)** — C++20 空间状态运行时：状态契约（版本链、定位健康度、执行租约、准入判定、故障注入）、语义 Token、ESN 时序记忆、端侧策略管理（候选策略验证后发布、可回滚）与任务编排。弱网传输调度和 DDS 协议生成尚未实现。

**定位安全与诊断**（分工：传感器层隔离 / 运行时恢复 / 事后诊断）
- **[SensorGuardNav-Runtime](https://github.com/zxinyu-robot/SensorGuardNav-Runtime)** — LiDAR 受污染时的定位自救：检测、可信度仲裁、七态状态机、安全速度上限与恢复门控；Python 实现，含故障注入与 JSONL 回放，目前只在合成数据上验证。
- **[SlamDoctor-Runtime](https://github.com/zxinyu-robot/SlamDoctor-Runtime)** — SLAM / 导航诊断 CLI：检查时间、坐标、频率和数据年龄契约，按故障图排序根因并给出下一步低成本排查，输出 JSON / Markdown / Mermaid 报告。
- **[legged-terrain-state](https://github.com/zxinyu-robot/legged-terrain-state)** — 四足混合地形的状态契约与安全降级：可通行性评分、风险分级，以及 Normal / ReduceSpeed / HoldPosition 三档安全模式。

**多机器人基础设施**
- **[swarm-spatial-link](https://github.com/zxinyu-robot/swarm-spatial-link)** — 多机协同 SLAM 工程的脱敏重构：按丢包 / 时延 / 队列把链路分为 Healthy / Constrained / Critical 三档，为位姿、关键帧、子图配置不同的 DDS QoS；另含时钟偏差估计与关键帧调度。
- **[multi-robot-map-fusion](https://github.com/zxinyu-robot/multi-robot-map-fusion)** — POSIX 共享内存关键帧通道（`shm_open` + `mmap`，序列号与校验和）和版本化子图注册表（幂等接收、约束校验、`graph_version` 递增）。

**学习基线**
- **[interactive-nav-learning](https://github.com/zxinyu-robot/interactive-nav-learning)** — 可中断导航学习基线：2D 环境中的行为克隆、DAgger 与中途语言纠正，CPU 上可复现。
- **[terrain-carry-rl](https://github.com/zxinyu-robot/terrain-carry-rl)** — Go2 + Piper 机械臂一体化强化学习脚手架：19 维动作、教师→学生蒸馏、域随机化与延迟模型；尚未接 Isaac Lab，没有训练结果。

> 标注"脱敏重构"的仓库是过往工程的公开重写，只包含可独立测试的核心；完整系统、厂商 SDK 与实机数据不公开。实现状态以各仓库的代码、测试和文档为准。

---

## 🧠 Research Agenda

这些问题从工程实践中逐步形成，仍在演进。我把当前的系统设计和学习机制视为待检验的假设，而不是最终方案。研究分为三个递进的层次。

### Layer 1 · Autonomous Systems

如何管理空间状态、任务契约、行为执行与故障恢复，使自主系统具备可验证、可恢复的运行能力。

**01 — State Reliability**

How should autonomous systems represent, validate and manage the lifecycle of spatial and decision-relevant states?

自主系统如何表达、验证与管理空间状态及决策相关信息的有效性、可信度和生命周期？

**02 — Experience and Adaptive Behavior**

How can robots accumulate reusable behavioral experience without blindly reusing outdated or context-inappropriate policies?

机器人如何积累可复用的行为经验，同时避免过时经验或错误策略迁移到不适用的场景？

*验证路径*：状态过期检测、重定位成功率、恢复时间、安全停车、任务完成率。

### Layer 2 · Multi-Agent Coordination

如何在异构能力、局部信息、通信约束与动态环境下，实现多智能体协同、任务分配与风险控制。

**03 — Resilient Multi-Agent Coordination**

How can heterogeneous agents coordinate and recover under partial observability, limited communication and conflicting constraints?

在局部可观测、通信受限及约束冲突的情况下，异构智能体如何保持协同并恢复正常运行？

*验证路径*：丢包与时延下的协同表现、通信开销、地图一致性、任务恢复能力。

### Layer 3 · Sociotechnical Systems

当自主智能体进入公共空间、生产系统与城市基础设施时，如何设计协作规则、责任边界与风险治理机制。

**04 — Authority and Accountability**

How should task authority, human intervention, escalation rules and accountability be distributed among autonomous agents, operators and institutions in shared environments?

在自主智能体与人、组织共同运行的环境中，任务权限、人工介入、升级处置和责任追踪，应如何在智能体、操作人员与组织之间配置？

*探索路径*：人工介入规则、任务授权、故障升级流程、决策与责任的可追溯性。

## 🧭 Research Approach

- **系统工程** — 定义状态、任务、权限与故障恢复的契约。
- **计算实验** — 真机、数据回放、可控故障注入与对照实验。
- **候选机制** — 语义状态 Token、时序 / 情景记忆（如 ESN）、端侧持续适应、世界模型；各自独立评估、可替换，而非预设的唯一路线。
- **社会技术分析**（计划中）— 结合 STS、Technology Policy 与 Computational Social Science，分析角色分工、运行规则、人工干预与责任机制如何影响智能系统的实际运行。

---

**欢迎交流**

**My guiding question:**

*How can we build autonomous intelligent systems that are not only capable of acting, but also reliable in execution, accountable in operation, and compatible with the societies they serve?*

如何构建不仅能够自主行动，而且能够可靠执行、追溯责任，并与其所服务的社会相协调的智能系统？

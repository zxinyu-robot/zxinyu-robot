# Hi, I'm Xinyu Zeng 👋

### Robotics & Spatial Intelligence · Reliable Autonomy · Multi-Agent Coordination · Sociotechnical Systems

[![Email](https://img.shields.io/badge/Email-zxiangsheng%40outlook.com-0A66C2?logo=microsoftoutlook)](mailto:zxiangsheng@outlook.com)

**中文** | [English](./README.en.md)

> **From Engineering Practice to Systems Thinking**
> 从通信工程出发，在无人系统与机器人领域开展自主导航、嵌入式系统与中间件研发，逐步走向智能系统的组织与治理。

---

## About Me

我是一名通信工程背景的机器人系统工程师，长期从事复杂环境下机器人自主系统的研发与工程实践，关注**空间状态、智能行为与系统协同**之间的关系。

从无 GPS 与弱网环境下的无人机，到动态环境中的足式机器人，再到空间状态与上层智能体之间的交互，我逐渐认识到：机器人智能不只是感知、规划或控制算法的组合，更涉及**状态如何被理解、行为如何被组织，以及不同主体如何在不确定环境中协同**。

我的实践可概括为三个阶段：

**第一阶段 · 让机器人在受限环境中自主运行**
基于几何 SLAM、传统路径规划与运动控制，通过状态机组织导航、任务执行与异常处理；覆盖 AGV、无 GPS 四旋翼、四足及双足机器人；处理无 GPS、弱网、强干扰与工业巡检等复杂环境；完成端侧嵌入式部署、系统集成与性能优化，并研发多机协同调度与导航任务执行系统。

**第二阶段 · 让机器人在动态环境中持续完成任务**
面向动态非结构化环境，利用端边协同资源分配构建导航中间件，解决四足机器人跨楼层、长航时目标导航等系统问题；关注定位、地图、规划、控制之间的状态一致性，以及任务中断后的故障检测、恢复与继续执行。

**第三阶段 · 从导航转向空间状态与智能行为的组织**
在前两阶段之上形成更高层抽象：机器人不应只依赖某一种地图、某一种规划算法或某一种智能模型，而应建立**不同层次空间信息之间的组织关系**——由此形成度量空间、符号空间、世界空间的认知框架，并探索世界空间状态的数据分发、版本与生命周期管理，以及机器人与上游世界模型的异步交互。

---

## Engineering Capabilities

按完整工程链路的组织能力划分，而非技术栈罗列：

| 能力领域 | 内容 |
| --- | --- |
| 机器人自主系统 | SLAM、导航、规划控制、行为调度、故障恢复 |
| 中间件与系统架构 | 消息通信、DDS、任务生命周期、状态管理、多机协同 |
| 嵌入式与端边协同 | Linux、C++、嵌入式部署、边端资源调度、系统集成 |
| 空间智能与交互 | 多空间状态表达、世界状态分发、模型与机器人异步交互 |

---

## Selected Engineering Work

三个代表性工作阶段；商业项目、实际工作与个人开源重构分开表述。

### 案例 A · 受限环境下的机器人自主系统

- **背景**：无 GPS、弱网断网、工业巡检等受限环境中的无人机与多机导航。
- **职责**：自主导航系统研发、状态机任务调度、多机协同调度、嵌入式部署与系统集成优化。
- **实现**：基于几何 SLAM 与传统运动控制，开发基于消息中间件的无 GPS 无人机导航任务执行中间件产品；参与军用飞行器导航模块研发。
- **结果**：覆盖 AGV、无 GPS 四旋翼、四足及双足等不同形态平台，在弱网、强干扰与室内外混合环境中交付。

### 案例 B · 动态环境下的足式机器人自主导航

- **背景**：动态非结构化环境中的四足机器人长航时、跨楼层目标导航。
- **职责**：端边协同资源分配、自研导航中间件、关键算法场景适配优化。
- **实现**：构建端边协同导航中间件，统一定位状态、任务契约、规划接口与故障恢复语义。
- **结果**：跨楼层闭环云端仿真 11/11 通过，真机在线建图与规划已运行（对应 [quadruped-crossfloor-nav-ws](https://github.com/zxinyu-robot/quadruped-crossfloor-nav-ws)）。

### 案例 C · 空间状态与智能系统交互

- **背景**：机器人的空间状态如何被上层智能体与世界模型可靠消费。
- **职责**：三空间认知框架的工程化、世界空间状态数据分发服务设计。
- **实现**：自研基于足式机器人世界空间状态的数据分发服务中间件，与上游世界模型进行异步状态任务导航行为交互。
- **结果**：公开重构为可构建、可测试的核心——状态契约、定位恢复、地形契约、弱网协同、共享内存融合、只读诊断。

---

## Current Focus

统一方向：**真实环境中的自主智能系统及其组织机制**。

三个研究尺度（递进）：

1. **单体智能** — 空间状态理解、自主行为、长期任务执行与故障恢复；
2. **群体智能** — 异构机器人、多智能体协同、信息共享与任务组织；
3. **社会技术系统** — 人机协作、权限分配、风险治理与责任追踪。

近期工作：

- **可靠自主导航**：四足跨楼层目标导航真机闭环已完成，当前对齐定位状态、任务契约、规划接口与故障恢复语义。
- **可复用空间运行时中间件**：让状态的来源、版本、置信度、有效期和失败语义被下游规划与执行模块明确理解。
- **弱网下的多机协同**：自适应通信与版本化子图融合，研究局部信息、通信延迟与数据不一致如何影响协同。

---

## Fork · Engineering Philosophy

Fork 不是一套要与现有系统竞争的技术路线，而是我在长期工程实践中逐渐形成的**工程价值观**。

- **技术应当服务于真实问题** — 不为技术而技术，不以复杂度衡量价值。
- **自主不等于失去约束** — 智能系统应当知道自己的状态、能力边界与行为权限。
- **可靠性来自可理解与可纠正** — 能够解释状态、识别异常、恢复运行，并允许撤销与回滚。
- **技术进步应当尊重人的利益** — 自动化不成为逃避责任的理由，效率不凌驾于安全之上。

> **佛科 · Fork —— 科技应当可靠，而不加害。**
>
> Fork，意为从既有系统中派生能力，通过拆分、组合、替换与演进，让技术能力具备可解释、可验证、可回滚的特性。
>
> 工程主张：**可解释 · 可验证 · 可替换 · 可回滚 · 可靠而不加害**

---

## How I Think About Systems

### 三空间：我如何理解机器人所处的世界

| 空间 | 回答的问题 | 描述 |
| --- | --- | --- |
| 度量空间 Metric | 我在哪里？周围有什么？可否通行？ | 定位、地图、几何关系、运动状态 |
| 符号空间 Symbolic | 对象是什么？什么关系？任务意味着什么？ | 语义、关系、约束、任务意义 |
| 世界空间 World | 系统所理解的世界处于什么状态？哪些可信、哪些可执行？ | 供自主系统、上层智能体与世界模型交互的任务相关状态 |

三空间是正在演进的系统认知框架，不等同于三种互斥的地图算法，也不把 World Space 与 World Model 混为一谈。

### 状态契约：我如何理解系统可靠性

状态不只是数据结构，还应包含：

- **来源与时间** — 从哪里产生、何时产生；
- **坐标系与版本** — 属于哪个空间基准与版本；
- **置信度与有效期** — 是否可信、是否过期；
- **生命周期** — 如何更新、失效与撤销；
- **权限与责任** — 谁可以使用、修改并依据它执行。

这一思想可继续延伸到任务契约、行为执行、故障恢复与多智能体协同。

### 研究尺度：我希望继续回答什么问题

自主智能体 → 多智能体系统 → 社会技术系统（详见 Research Agenda）。

---

## Research Agenda

这些问题从工程实践中逐步形成，仍在演进。我把当前的系统设计和学习机制视为待检验的假设，而非最终方案。

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

### Research Approach

- **系统工程** — 定义状态、任务、权限与故障恢复的契约。
- **计算实验** — 真机、数据回放、可控故障注入与对照实验。
- **候选机制** — 语义状态 Token、时序/情景记忆、端侧持续适应、世界模型；各自独立评估、可替换，而非预设唯一路线。
- **社会技术分析**（计划中）— 结合 STS、Technology Policy 与 Computational Social Science，分析角色分工、运行规则、人工干预与责任机制。

---

## Open Source Projects

> 公开仓库均可构建、可测试；标注 ▶ 的附可运行 demo。商业项目与生产系统不公开，此处只放可独立测试的核心重构。

**▶ Demo 速览（终端回放）**

| 仓库 | 运行命令 | 展示内容 |
| --- | --- | --- |
| legged-navigation-runtime | `./build/default/recovery_demo` | 定位失效 → 搜索 → 配准 → 恢复 |
| swarm-spatial-link | `./build/default/weak_link_demo` | 弱网三态 QoS 自适应 |
| fork-spatial-runtime | `./build/default/examples/cpp/runtime_demo` | 图事务与状态生命周期 |
| multi-robot-map-fusion | `./build/default/fusion_demo` | 共享内存 + 子图登记 |
| legged-terrain-state | `./build/default/terrain_demo` | 地形风险分级与安全模式 |
| SlamDoctor-Runtime | `slam-doctor diagnose examples/nav_oscillation.jsonl` | 八类症状根因排查 |

**三个平台的端侧系统**

| 平台 | 仓库 | 当前验证程度 | Demo |
| --- | --- | --- | --- |
| Unitree Go2 四足 | quadruped-crossfloor-nav-ws | 云端仿真跨楼层闭环 11/11；真机在线建图与规划 | ▶ 视频见仓库 `docs/media/` |
| Unitree G1 / H2 双足 | legged-navigation-runtime | 脱敏重构：定位恢复核心 + 单元测试 | ▶ recovery_demo |
| 复合清洁机器人 | CleanRobot-Sim2Real-skill | MuJoCo 仿真，尚未上真机 | — |

**跨平台空间运行时**

- [ForkSpatial-Runtime-Engine](https://github.com/zxinyu-robot/ForkSpatial-Runtime-Engine) — C++20 空间状态运行时：状态契约、语义 Token、ESN 时序记忆、端侧策略管理与任务编排。

**定位安全与诊断**

- [SensorGuardNav-Runtime](https://github.com/zxinyu-robot/SensorGuardNav-Runtime) — LiDAR 受污染时的定位自救：检测、可信度仲裁、七态状态机、安全速度上限与恢复门控。
- [SlamDoctor-Runtime](https://github.com/zxinyu-robot/SlamDoctor-Runtime) — SLAM/导航诊断 CLI：契约检查、故障图根因排序、下一步低成本排查，输出 JSON/Markdown/Mermaid。
- [legged-terrain-state](https://github.com/zxinyu-robot/legged-terrain-state) — 四足混合地形状态契约与安全降级：可通行性评分、风险分级、Normal/ReduceSpeed/HoldPosition。

**多机器人基础设施**

- [swarm-spatial-link](https://github.com/zxinyu-robot/swarm-spatial-link) — 弱网自适应通信：Healthy/Constrained/Critical 三态 QoS、时钟偏差估计、关键帧调度。
- [multi-robot-map-fusion](https://github.com/zxinyu-robot/multi-robot-map-fusion) — POSIX 共享内存关键帧通道与版本化子图注册表（幂等接收、约束校验、graph_version 递增）。

**学习基线**

- [interactive-nav-learning](https://github.com/zxinyu-robot/interactive-nav-learning) — 可中断导航学习：2D 环境行为克隆、DAgger 与中途语言纠正。
- [terrain-carry-rl](https://github.com/zxinyu-robot/terrain-carry-rl) — Go2 + Piper 一体化 RL 脚手架：19 维动作、教师→学生蒸馏、域随机化与延迟模型。

> 标注"脱敏重构"的仓库是过往工程的公开重写，只含可独立测试的核心；完整系统、厂商 SDK 与实机数据不公开。实现状态以各仓库代码、测试与文档为准。

---

## 欢迎交流

佛科目前由我个人发起与维护；认同这份价值观、愿意一起长期共建的伙伴，欢迎加入。

**My guiding question:**

*How can we build autonomous intelligent systems that are not only capable of acting, but also reliable in execution, accountable in operation, and compatible with the societies they serve?*

如何构建不仅能够自主行动，而且能够可靠执行、追溯责任，并与其所服务的社会相协调的智能系统？

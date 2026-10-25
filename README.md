<div align="center">

# Hi, I'm Xinyu Zeng（曾欣宇）👋

### Robotics Systems · Spatial Intelligence · Multi-Agent Systems · Sociotechnical Governance

[![Email](https://img.shields.io/badge/Email-zxiangsheng%40outlook.com-0A66C2?logo=microsoftoutlook)](mailto:zxiangsheng@outlook.com)

</div>

我关注自主机器人与空间智能系统如何从单体自主运行走向异构多智能体协同，以及这些系统进入真实社会后，如何实现可靠执行、协同决策、风险控制与责任追踪。

我的工程实践围绕机器人自主导航、空间状态管理、任务执行与边缘系统展开。目前，我正尝试将这些工程问题延伸到多智能体协作、社会技术系统（Sociotechnical Systems）与未来社会治理的交叉研究中。

> **From autonomous robots to governed intelligent systems.**
>
> 从机器人的自主运行，到开放环境中智能系统的协同与治理。

---

## 🔭 Research Vision

我的长期目标是探索面向真实环境的自主智能体运行机制，以及智能系统与人类、组织和公共基础设施之间的协作关系。

我关注三个相互关联的层次：

- **Autonomous Systems** — 如何管理空间状态、任务契约、行为执行与故障恢复，使自主系统具备可验证、可恢复的运行能力。
- **Multi-Agent Coordination** — 如何在异构能力、局部信息、通信约束与动态环境下，实现多智能体协同、任务分配与风险控制。
- **Sociotechnical Governance** — 当自主智能体进入公共空间、生产系统与城市基础设施时，如何设计协作规则、责任边界与风险治理机制。

我希望以真实机器人系统为工程基础，将系统设计、计算实验与社会科学研究相结合，理解技术架构如何影响协作行为、组织决策与治理实践。

## 🛠️ Engineering Focus

我的工程目标不只是单点算法精度，而是让定位、地图、通信、边缘算力、任务规划和安全控制在资源受限的真机上形成稳定闭环：

```text
LiDAR / IMU / Vision
        ↓
Localization & Mapping
        ↓
Spatial State Runtime（状态契约 · 可信度 · 生命周期）
        ↓
Multi-Robot Communication & Edge Fusion
        ↓
BehaviorTree Runtime / Local Safety Controller（执行 · 失败检测 · 恢复）
```

过往工程覆盖 AGV、无 GPS 四旋翼、四足/双足机器人，以及弱网、无 GPS、强干扰和室内外混合场景。

### 1. Robotics & Spatial Intelligence

- LiDAR–IMU State Estimation and SLAM
- Spatial Mapping, Traversability and State Representation
- Robot Navigation, Trajectory Planning and Execution
- Behavior Trees (BT), Task Orchestration and Recovery
- Legged Robotics and GPS-Denied Autonomous Navigation

### 2. Robotics Middleware & Edge Systems

- C++14/17/20, Python, Linux
- ROS 2, RMW, DDS and QoS
- State Contracts, Resource Lifecycle and Interface Design
- Fault Detection, Execution Monitoring and Recovery
- Edge Deployment, Heterogeneous Computing and Weak-Network Operation

### 3. Multi-Agent Systems

- Heterogeneous Robot Coordination
- Distributed State Exchange and Spatial Information Sharing
- Task Assignment, Capability Interfaces and Execution Constraints
- Resilient Coordination under Communication Failures

## 🧩 Selected Projects

### [MotionSLAM_ws](https://github.com/zxinyu-robot/MotionSLAM_ws)

**Legged Robot Autonomy & Navigation**

围绕四足机器人自主导航与系统集成，探索空间状态估计、地图处理、路径与轨迹规划、行为树任务编排及底层运动执行之间的协作机制。

**Focus:** Spatial State · Navigation · BT-Based Orchestration · Motion Execution

### [legged-navigation-runtime](https://github.com/zxinyu-robot/legged-navigation-runtime)

**Fault-Tolerant Legged Navigation Runtime**

关注腿式机器人导航过程中的状态可靠性、故障诊断、任务恢复与跨楼层导航问题，探索从单次规划成功走向可持续运行的自主导航系统。

**Focus:** Fault Tolerance · State Validity · Recovery · Multi-Floor Navigation

### [fork-spatial-runtime](https://github.com/zxinyu-robot/fork-spatial-runtime)

**Spatial State & Autonomous Behavior Runtime**

探索空间状态、任务契约、模块依赖与执行生命周期之间的运行时机制，尝试为不同机器人和自主系统提供可复用的基础能力。

**Focus:** State Contracts · Lifecycle Management · Execution Governance · Runtime Architecture

### Multi-Agent Spatial Coordination

[swarm-spatial-link](https://github.com/zxinyu-robot/swarm-spatial-link) · [multi-robot-map-fusion](https://github.com/zxinyu-robot/multi-robot-map-fusion)

围绕异构多机器人之间的空间状态交换、通信约束与协作执行，探索如何通过明确的状态与任务接口，提高分布式自主系统的协同能力与可恢复性。前者是面向弱网的自适应通信中间件核心，后者是共享内存数据路径与版本化子图融合核心。

**Focus:** Multi-Robot Coordination · Distributed State · Edge Autonomy

### Other Projects

- [legged-terrain-state](https://github.com/zxinyu-robot/legged-terrain-state) — 腿式机器人地形状态契约、可通行性评估与安全降级
- [interactive-nav-learning](https://github.com/zxinyu-robot/interactive-nav-learning) — 支持中途纠正的行为克隆与 DAgger 导航学习基线
- [SlamDoctor](https://github.com/zxinyu-robot/SlamDoctor) — 基于运行证据与故障图的 SLAM / 导航诊断 CLI

> 以上项目反映不同层次的工程探索。具体功能、实现状态与实验结果以各仓库中的代码、文档和测试为准。

## 🧠 Current Research Questions

我尤其关注以下问题：

**01 — State Reliability**

How should autonomous systems represent, validate and manage the lifecycle of spatial and decision-relevant states?

自主系统如何表达、验证与管理空间状态及决策相关信息的有效性、可信度和生命周期？

**02 — Experience and Adaptive Behavior**

How can robots accumulate reusable behavioral experience without blindly reusing outdated or context-inappropriate policies?

机器人如何积累可复用的行为经验，同时避免过时经验或错误策略迁移到不适用的场景？

**03 — Resilient Multi-Agent Coordination**

How can heterogeneous agents coordinate and recover under partial observability, limited communication and conflicting constraints?

在局部可观测、通信受限及约束冲突的情况下，异构智能体如何保持协同并恢复正常运行？

**04 — Intelligent Systems and Social Governance**

How should coordination rules, operational authority, risk management and accountability evolve as autonomous agents enter shared public environments?

随着自主智能体进入公共空间与关键基础设施，协作规则、运行权限、风险管理与责任划分应如何设计和演进？

## 🧪 Emerging Technical Directions

我正在探索以下技术方向，并将它们视为可独立验证、可替换的研究方法，而非预设的唯一技术路线。

- **Semantic State Tokens** — 几何与环境状态的语义化表达，以及状态资源的组织与生命周期管理。
- **Temporal and Episodic Memory** — 基于 ESN、事件记录或其他时序模型的行为记忆与场景经验复用。
- **Edge-Side Adaptation** — 资源受限、通信中断条件下的策略选择、执行反馈与持续适应。
- **World Models** — 对环境变化与动作后果进行预测，为规划、风险评估与恢复决策提供辅助信息。

我关注的核心不是简单叠加不同模型，而是研究它们如何与真实机器人运行时衔接，以及如何通过可复现的实验验证其实际收益、适用边界和失败模式。

## 🌐 Beyond Engineering

机器人是我理解更广泛智能系统问题的起点，而不是研究范围的终点。

当自主系统开始参与生产、服务、基础设施运营和公共空间活动时，许多传统的工程问题会进一步成为组织与治理问题：

- 谁能够分配任务、定义规则和改变执行优先级？
- 当多个自主系统相互依赖时，风险如何传播，故障如何追踪？
- 当自动化规则影响公共资源与空间使用时，如何权衡效率、安全与公平？
- 工程架构、组织制度和人类行为之间，如何形成可解释、可验证的协作机制？

我希望逐步结合 **Science and Technology Studies (STS)、Technology Policy、Computational Social Science 与 Sociotechnical Systems Research**，研究自主智能系统与真实社会之间的互动关系。

## 📌 Current Priorities

- 推进真实机器人自主导航与跨楼层场景验证。
- 完善空间状态、任务契约、生命周期与故障恢复机制。
- 探索可复用的异构多智能体协作接口与边侧运行机制。
- 将工程问题提炼为可验证的研究问题，并逐步引入社会科学理论与研究方法。

## 🤝 Collaboration

欢迎围绕以下主题交流：

- Robotics Systems and Spatial Intelligence
- Embodied AI Infrastructure and Multi-Agent Systems
- Distributed Autonomy and Resilient Edge Computing
- Human–Robot Interaction and Social Norms
- Science and Technology Studies, Technology Policy and AI Governance

**My guiding question:**

*How can we build autonomous intelligent systems that are not only capable of acting, but also reliable in execution, accountable in operation, and compatible with the societies they serve?*

如何构建不仅能够自主行动，而且能够可靠执行、追溯责任，并与其所服务的社会相协调的智能系统？

---

- Email: [zxiangsheng@outlook.com](mailto:zxiangsheng@outlook.com)
- GitHub: [@zxinyu-robot](https://github.com/zxinyu-robot)

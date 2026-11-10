# Hi, I'm Xinyu Zeng 👋

### Robotics & Spatial Intelligence · Reliable Autonomy · Multi-Agent Coordination · Sociotechnical Systems

[![Email](https://img.shields.io/badge/Email-zxiangsheng%40outlook.com-0A66C2?logo=microsoftoutlook)](mailto:zxiangsheng@outlook.com)
[![Hugging Face](https://img.shields.io/badge/%F0%9F%A4%97%20Hugging%20Face-RobotPelicans-FFD21E)](https://huggingface.co/RobotPelicans)

**中文** | [English](./README.en.md)

## Technical Wiki

个人技术体系、工程价值观、项目关系、工程案例和验证方法统一整理在 Wiki：

**[进入技术 Wiki →](https://github.com/zxinyu-robot/zxinyu-robot/wiki)**

- [Technical System](https://github.com/zxinyu-robot/zxinyu-robot/wiki/Technical-System)
- [Engineering Values](https://github.com/zxinyu-robot/zxinyu-robot/wiki/Engineering-Values)
- [Project Map](https://github.com/zxinyu-robot/zxinyu-robot/wiki/Project-Map)
- [Engineering Cases](https://github.com/zxinyu-robot/zxinyu-robot/wiki/Engineering-Cases)

---

## About Me

> **From Engineering Practice to Systems Thinking**
>
> 从通信工程出发，我持续参与无人系统与机器人自主系统研发和项目产品交付，工程实践涵盖无 GPS、弱网、强干扰与室内外混合动态环境下的自主导航、嵌入式系统与中间件；过往涉及 AGV、无 GPS 四旋翼、四足及双足等不同形态平台。
>
> 随着实践从底层状态估计与系统实现，逐步延伸至空间状态和上层智能体的交互，我的关注点也从单一算法转向智能系统的组织机制：**如何理解和管理空间状态、组织智能行为，并推动不同主体在不确定环境中可靠协同。**

---

## Selected Engineering Work

三个代表性工作阶段；商业项目、实际工作与个人开源重构分开表述。

### 案例 A · 受限环境下的无人飞行器自主导航

无 GPS、弱网/断网和工业巡检场景中的无人机自主导航案例。工程说明与演示素材已迁移到 [uav](https://github.com/zxinyu-robot/uav)，详见其 [`docs/demo-case-a.md`](https://github.com/zxinyu-robot/uav/blob/main/docs/demo-case-a.md)。

### 案例 B · 动态环境下的足式机器人跨楼层长航时自主导航

Unitree Go2 跨楼层自主导航闭环：端边协同、空间状态、任务契约与故障恢复。实现与演示已归档到 [quadruped-crossfloor-nav-ws](https://github.com/zxinyu-robot/quadruped-crossfloor-nav-ws)，详见其 [`docs/demo-case-b.md`](https://github.com/zxinyu-robot/quadruped-crossfloor-nav-ws/blob/main/docs/demo-case-b.md)。

### 案例 C · 空间状态与智能系统交互

围绕状态契约、执行租约、空间状态和上层智能体交互的公开重构。工程说明已迁移到 [ForkSpatial-Runtime-Engine](https://github.com/zxinyu-robot/ForkSpatial-Runtime-Engine)，详见其 [`docs/demo-case-c.md`](https://github.com/zxinyu-robot/ForkSpatial-Runtime-Engine/blob/main/docs/demo-case-c.md)。

---

## Current Work

统一方向：**真实环境中的自主智能系统及其组织机制**。

### 公共底座 · 空间状态与契约

- **[ForkSpatial-Runtime-Engine](https://github.com/zxinyu-robot/ForkSpatial-Runtime-Engine)** — 状态契约、执行租约与空间状态运行时。
- **[spatial-map-foundation](https://github.com/zxinyu-robot/spatial-map-foundation)** — 地图瓦片、空间锚定与版本化状态事务。

### 1 · 单体智能

- **[quadruped-crossfloor-nav-ws](https://github.com/zxinyu-robot/quadruped-crossfloor-nav-ws)** — Go2 四足机器人跨楼层导航真机闭环。
- **[legged-navigation-runtime](https://github.com/zxinyu-robot/legged-navigation-runtime)** — 足式导航运行时、故障恢复与诊断集成。
- **[SlamDoctor-Runtime](https://github.com/zxinyu-robot/SlamDoctor-Runtime)** — 面向机器人自主系统日志的离线诊断工具。

### 2 · 群体智能

- **[swarm-adapter-foundation](https://github.com/zxinyu-robot/swarm-adapter-foundation)** — 多机状态、地图与指令契约，以及弱网通信和子图融合。

### 3 · 社会技术系统

暂无独立仓库。相关机制分布在状态契约、故障恢复、人工接管学习和运行时执行语义中。

详细系统观、研究议程和工程原则见：

- [Systems Perspective](docs/systems-perspective.md)
- [Research Agenda](docs/research-agenda.md)
- [Engineering Philosophy](docs/engineering-philosophy.md)

---

## Public Collaboration

当前所有 `Current Work` 项目都开放不同层次的参与。

优先协作入口：

- **[SlamDoctor-Runtime](https://github.com/zxinyu-robot/SlamDoctor-Runtime)** — 离线诊断、ROS 2 / rosbag2 / MCAP 适配与故障案例。
- **[legged-navigation-runtime](https://github.com/zxinyu-robot/legged-navigation-runtime)** — 故障恢复、运行时诊断和导航系统集成。
- **[ForkSpatial-Runtime-Engine](https://github.com/zxinyu-robot/ForkSpatial-Runtime-Engine)** — 状态契约、执行语义和运行时接口。
- **[swarm-adapter-foundation](https://github.com/zxinyu-robot/swarm-adapter-foundation)** — 多机 Adapter、DDS、弱网 QoS 和子图融合。

没有真实机器人也可以参与：从离线日志、测试、文档和可复现案例开始。

**Discussion first. Implementation second. Validation throughout.**

---

## Open Source Projects

- **Runtime & Spatial State** — [ForkSpatial-Runtime-Engine](https://github.com/zxinyu-robot/ForkSpatial-Runtime-Engine) · [spatial-map-foundation](https://github.com/zxinyu-robot/spatial-map-foundation)
- **Navigation & Reliability** — [SlamDoctor-Runtime](https://github.com/zxinyu-robot/SlamDoctor-Runtime) · [legged-navigation-runtime](https://github.com/zxinyu-robot/legged-navigation-runtime) · [quadruped-crossfloor-nav-ws](https://github.com/zxinyu-robot/quadruped-crossfloor-nav-ws)
- **Multi-Robot Systems** — [swarm-adapter-foundation](https://github.com/zxinyu-robot/swarm-adapter-foundation)
- **Embodied Learning** — [embodied-learning-baselines-](https://github.com/zxinyu-robot/embodied-learning-baselines-)
- **Tools** — [KMZ-editor](https://github.com/zxinyu-robot/KMZ-editor)

历史项目已逐步并入上述主线或归档；当前实现状态以活跃仓库代码和测试为准。

---

## Systems Perspective

我关注能够被理解、验证、恢复和外部审查的自主系统。

- 状态应包含来源、时间、坐标系、版本、置信度、有效期和权限。
- 自主系统不仅要行动，也要知道何时不可信、如何降级和恢复。
- 工程结论应由真实问题、可复现证据和外部反馈支持。

深入阅读：

- [Systems Perspective](docs/systems-perspective.md)
- [Research Agenda](docs/research-agenda.md)
- [Engineering Philosophy](docs/engineering-philosophy.md)
- [Community & Collaboration](docs/community-and-collaboration.md)

---

## Contact

- [Hugging Face · RobotPelicans](https://huggingface.co/RobotPelicans)
- [微信公众号 · 佛科思想录](https://mp.weixin.qq.com/s/P-YrXc1eNrKBHbHvUd07pQ)
- 技术讨论、复现反馈和协作意向，欢迎通过相关仓库 Issue 或邮件联系。

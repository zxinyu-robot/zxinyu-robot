# Research Agenda

这些问题从真实工程实践中逐步形成，仍然是待检验的研究假设，而不是预设完成的方案。

## Reliable Autonomous Systems

如何管理空间状态、任务契约、行为执行与故障恢复，使自主系统具备可观察、可诊断和可恢复的运行能力。

关联项目：

- [SlamDoctor-Runtime](https://github.com/zxinyu-robot/SlamDoctor-Runtime)
- [legged-navigation-runtime](https://github.com/zxinyu-robot/legged-navigation-runtime)
- [quadruped-crossfloor-nav-ws](https://github.com/zxinyu-robot/quadruped-crossfloor-nav-ws)

## Collaborative Intelligence

如何在异构能力、局部信息、通信约束和动态环境下，实现多智能体协同、任务分配与风险控制。

关联项目：

- [ForkSpatial-Runtime-Engine](https://github.com/zxinyu-robot/ForkSpatial-Runtime-Engine)
- [swarm-adapter-foundation](https://github.com/zxinyu-robot/swarm-adapter-foundation)

## Sociotechnical Systems

当自主系统进入公共空间、生产系统和城市基础设施时，如何设计协作规则、权限边界、人工介入和责任追踪机制。

当前相关机制分布在状态契约、故障恢复、人工接管学习和运行时执行语义中，尚未形成独立仓库。

## Research Approach

- **系统工程** — 定义状态、任务、权限和故障恢复契约。
- **计算实验** — 使用真机、数据回放、可控故障注入和对照实验。
- **外部验证** — 通过真实使用、代码评审和社区反馈修正设计。
- **社会技术分析** — 逐步研究角色分工、运行规则、人工干预和责任机制。

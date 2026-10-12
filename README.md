<div align="center">

# 曾欣宇 | Robotics Systems Engineer

多机器人协同 · 空间智能导航 · 边缘计算

**Multi-Robot Coordination · Spatial Intelligence Navigation · Edge Computing**

面向资源受限真机，构建从多传感器感知、空间状态管理、端边通信到任务安全执行的机器人运行时基础设施。

[![Email](https://img.shields.io/badge/Email-zxiangsheng%40outlook.com-0A66C2?logo=microsoftoutlook)](mailto:zxiangsheng@outlook.com)

</div>

## 我解决的问题

我关注的不只是单点算法精度，而是如何让定位、地图、通信、边缘算力、任务规划和安全控制在真实机器人上形成稳定闭环：

```text
LiDAR / IMU / Vision
        ↓
Localization & Mapping
        ↓
Spatial State Runtime
        ↓
Multi-Robot Communication & Edge Fusion
        ↓
BehaviorTree / Nav2 / Local Safety Controller
```

过往工程覆盖 AGV、无 GPS 四旋翼、四足/双足机器人，以及弱网、无 GPS、强干扰和室内外混合场景。

## 代表项目

### 系统级工程

- [MotionSLAM_ws](https://github.com/zxinyu-robot/MotionSLAM_ws) — Go2 上的 Super-LIO、全局粗引导、SCAN 局部规划、行为树编排与本地安全执行集成栈

### 中间件与运行时

- [Fork Spatial Runtime](https://github.com/zxinyu-robot/fork-spatial-runtime) — 增量空间状态、因子校验与原子图事务运行时
- [Swarm Spatial Link](https://github.com/zxinyu-robot/swarm-spatial-link) — 面向多机器人弱网协同的自适应通信中间件
- [Multi-Robot Map Fusion](https://github.com/zxinyu-robot/multi-robot-map-fusion) — 共享内存数据路径与版本化子图融合核心

### 导航与安全

- [Legged Navigation Runtime](https://github.com/zxinyu-robot/legged-navigation-runtime) — 双足机器人故障恢复定位与多楼层导航运行时
- [Legged Terrain State](https://github.com/zxinyu-robot/legged-terrain-state) — 四足机器人地形状态契约、可通行性评估与安全降级

### 学习与诊断

- [Interactive Nav Learning](https://github.com/zxinyu-robot/interactive-nav-learning) — 支持中途纠正的行为克隆与 DAgger 导航学习基线
- [SlamDoctor](https://github.com/zxinyu-robot/SlamDoctor) — 基于运行证据与故障图的 SLAM 导航诊断 CLI

## 联系方式

- Email: [zxiangsheng@outlook.com](mailto:zxiangsheng@outlook.com)
- GitHub: [@zxinyu-robot](https://github.com/zxinyu-robot)

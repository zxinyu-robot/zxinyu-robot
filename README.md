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

## 核心能力三角

### 空间智能导航

LiDAR-IMU 状态估计、TF/坐标契约、多层地图、自动重定位、全局/局部规划与导航控制闭环。

### 通信协同

ROS 2、DDS QoS、共享内存、时间同步、多机器人空间消息契约、弱网关键帧调度与边缘地图融合。

### 边缘计算

Jetson Orin、RK3588/RK NPU、Docker、并发与异步数据流、拷贝治理、端边算力分层和性能观测。

## 代表项目

### [Legged Navigation Runtime](https://github.com/zxinyu-robot/legged-navigation-runtime)

面向 Unitree G1/H2 级双足机器人的故障恢复定位与多楼层导航运行时。公开实现自动重定位状态机、配准结果门控、安全停车、连续健康帧恢复确认和 P95 延迟统计，并说明 FAST-LIO2、Scan Context、NDT/ICP、Localizer 与 Nav2 的工程集成边界。

### [Legged Terrain State](https://github.com/zxinyu-robot/legged-terrain-state)

面向四足机器人混合地形导航的状态契约与安全降级核心。公开实现 BaseState/TerrainState/ContactState、可通行性评分、风险分级及感知退化时的降速与停车策略。

### [Swarm Spatial Link](https://github.com/zxinyu-robot/swarm-spatial-link)

面向多机器人协同定位与地图融合的网络自适应通信中间件核心。公开实现 DDS QoS 自适应、关键帧调度、鲁棒时钟偏差估计和统一空间消息契约，并说明 802.11s Mesh、共享内存、Graph-SLAM 与边缘融合的工程边界。

### [Multi-Robot Map Fusion](https://github.com/zxinyu-robot/multi-robot-map-fusion)

面向多机器人 3D 地图协同的共享内存数据路径与版本化子图融合核心。公开实现 POSIX 共享内存帧槽、只读零中间拷贝视图、子图身份、约束校验和图版本管理。

### [Fork Spatial Runtime](https://github.com/zxinyu-robot/fork-spatial-runtime)

与优化器后端解耦的 C++20 增量空间状态运行时。公开实现状态生命周期、因子批次校验、原子图事务、固定延迟窗口和可替换优化后端接口。

### [SlamDoctor](https://github.com/zxinyu-robot/SlamDoctor)

基于接口契约、运行证据和可执行故障图的 SLAM 导航诊断 CLI。支持跨层健康检查、八类故障症状、根因假设排序、下一步 Probe 推荐及 Mermaid/DOT/Markdown 报告。

## 能力成熟度

### 已用于工程交付

- FAST-LIO/Faster-LIO、Nav2、A*、Ego-Planner、PCT-Planner 等导航链路集成。
- ROS 2/DDS 通信治理、Linux 共享内存与 Jetson/RK3588 边缘部署。
- 无 GPS 定位、自动重定位、地图融合、任务恢复和系统问题排查。

### 已有公开原型

- 增量空间状态 Runtime 与优化后端事务接口。
- 双足机器人定位失效恢复与安全执行监督器。
- 四足机器人地形状态契约、可通行性评估与安全降级核心。
- 多机器人弱网 QoS、关键帧调度和时钟一致性核心。
- POSIX 共享内存关键帧数据路径与版本化子图融合核心。
- SLAM 导航接口契约检查与可执行故障图诊断工具。

### 正在探索

- 空间策略记忆：以可版本、可检索、可回滚的文本保存“场景—策略—结果”。
- World Action Model / World Model 与技能级任务契约、BehaviorTree 的受约束交互。
- 语义查询驱动的自主探索、多 Agent-VLA 协同与多层地图 token 化。

探索方向不直接控制速度或关节；模型只生成技能级建议，本地行为树和安全控制器保留最终执行权。

## 技术栈

`C++17/20` · `Python` · `C` · `ROS 2` · `DDS` · `GTSAM`<br>
`PCL` · `OpenCV` · `BehaviorTree.CPP` · `Docker` · `Jetson Orin` · `RKNN/TensorRT`

## 工程原则

- 明确区分已经交付、公开原型和研究探索。
- 用可运行 Demo、自动化测试、实验口径和失败边界证明能力。
- 空间几何是底座，空间状态是契约，行为树负责调度，本地控制器守住安全边界。
- 大模型用于状态推理和策略建议，不绕过机器人实时控制链路。

## 联系方式

- Email: [zxiangsheng@outlook.com](mailto:zxiangsheng@outlook.com)
- GitHub: [@zxinyu-robot](https://github.com/zxinyu-robot)

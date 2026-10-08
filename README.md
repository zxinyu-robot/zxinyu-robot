<div align="center">

# 曾欣宇 | Robotics Software Engineer

机器人空间状态中间件 · SLAM/导航工程化 · 边缘异构计算

Building runtime infrastructure from **Perception → Spatial State → Task Planning → Safe Execution**

[![Email](https://img.shields.io/badge/Email-zxiangsheng%40outlook.com-0A66C2?logo=microsoftoutlook)](mailto:zxiangsheng@outlook.com)

</div>

## 目前关注

我主要使用 C++ 构建机器人空间计算基础设施，关注多传感器状态如何在资源受限设备上被可靠地产生、传输、融合并交付给任务规划与执行模块。
1. 基于⼤语⾔模型WAM/WM的状态推理与预测规划 → 通过中间件与底层⾏为树交互形成⾃主导航闭环控制
2. 多层地图⽣产与消费、⾏为树任务编排与实时控制闭环，在Jetson Orin/RK3588等受限平台上实现从"空间感知→状态推理→⾏动决策"的低延迟架构落地

- 增量状态空间：状态生命周期、因子注入、滑动窗口和边缘化。
- 定位与导航：LiDAR-IMU 状态估计、地图接口、全局/局部规划链路。
- 机器人中间件：ROS 2、DDS QoS、任务契约与 BehaviorTree.CPP。
- 边缘部署：Jetson Orin、RK NPU、Docker、TensorRT/RKNN。

## 代表项目

### [Legged Navigation Runtime](https://github.com/zxinyu-robot/legged-navigation-runtime)

面向 Unitree G1/H2 级双足机器人的故障恢复定位与多楼层导航运行时。公开实现自动重定位状态机、配准结果门控、安全停车、连续健康帧恢复确认和 P95 延迟统计，并说明 FAST-LIO2、Scan Context、NDT/ICP、Localizer 与 Nav2 的工程集成边界。

### [Swarm Spatial Link](https://github.com/zxinyu-robot/swarm-spatial-link)

面向多机器人协同定位与地图融合的网络自适应通信中间件核心。公开实现 DDS QoS 自适应、关键帧调度、鲁棒时钟偏差估计和统一空间消息契约，并说明 802.11s Mesh、共享内存、Graph-SLAM 与边缘融合的工程边界。

### [Fork Spatial Runtime](https://github.com/zxinyu-robot/fork-spatial-runtime)

与优化器后端解耦的 C++20 增量空间状态运行时。目前已实现状态生命周期、因子批次校验、原子图事务、固定延迟窗口和可替换优化后端接口，并通过 Linux/macOS CI 验证。

### SlamDoctor（构建中）

面向 SLAM 工程联调的数据质量诊断工具，计划覆盖时间戳、TF 链、轨迹误差和定位健康度检查。达到可重复运行的首个版本后再作为正式项目发布。

## 技术栈

`C++17/20` · `Python` · `ROS 2` · `DDS` · `GTSAM` · `PCL` · `OpenCV`<br>
`BehaviorTree.CPP` · `Docker` · `Jetson Orin` · `TensorRT` · `RKNN`

## 工程原则

- 区分已经实现、经过验证和仍在规划的能力。
- 用最小可运行示例、自动化测试和实验方法说明项目，而不是只展示架构图。
- 让感知、状态估计、任务决策和安全执行通过稳定契约解耦。

## 联系方式

- Email: [zxiangsheng@outlook.com](mailto:zxiangsheng@outlook.com)
- GitHub: [@zxinyu-robot](https://github.com/zxinyu-robot)

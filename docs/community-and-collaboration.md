# Community and Collaboration

开源不只是个人技术能力的展示，也不是让 AI 独立构建一个封闭的技术世界。

真正的协作应该让其他工程师能够：

- 使用；
- 质疑；
- 修改；
- 验证；
- 贡献。

## 协作层次

```text
离线日志和文档
    ↓
适配器与测试
    ↓
运行时集成
    ↓
真实机器人验证
    ↓
跨项目协作和共同维护
```

## 当前入口

- [SlamDoctor-Runtime](https://github.com/zxinyu-robot/SlamDoctor-Runtime) — 离线诊断、故障案例和数据适配。
- [legged-navigation-runtime](https://github.com/zxinyu-robot/legged-navigation-runtime) — 恢复机制和导航运行时集成。
- [ForkSpatial-Runtime-Engine](https://github.com/zxinyu-robot/ForkSpatial-Runtime-Engine) — 状态契约和执行语义。
- [swarm-adapter-foundation](https://github.com/zxinyu-robot/swarm-adapter-foundation) — 多机通信、弱网 QoS 和子图融合。

没有真实机器人也可以从离线日志、测试、文档和可复现案例开始。

## 协作原则

- 讨论先行，实现其次，持续验证；
- 每个工程结论都应有可观察证据；
- 贡献不要求参与者先接受完整理论框架；
- 外部反馈可以推翻原有设计；
- 比起 Stars，更重视有人真正使用、讨论和修改这些工作。

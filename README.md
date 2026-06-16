# 🤖 Local AI Infrastructure

> 在 MacBook Air 上运行的多模型 Agent 环境——本地推理 + 云端 API + 多渠道 Agent 调度。

---

## Architecture / 架构

```
┌─────────────────────────────────────────────┐
│              OpenClaw Agent Platform         │
│         (多渠道调度 · 记忆 · 心跳巡检)        │
└──────────┬──────────────────┬───────────────┘
           │                  │
    ┌──────▼──────┐    ┌──────▼──────┐
    │  本地推理    │    │  云端 API   │
    │ Ollama      │    │  DeepSeek   │
    │ Qwen3 14B   │    │ Chat/Reason │
    └─────────────┘    └─────────────┘
           │                  │
    ┌──────▼──────────────────▼───────┐
    │         接入渠道                 │
    │  WhatsApp · Terminal · ...      │
    └─────────────────────────────────┘
```

---

## Models / 模型配置

| 模型 | 方式 | 使用场景 |
|------|------|----------|
| **Qwen3 14B** | Ollama 本地推理 | 隐私敏感任务 · 离线场景 · 零 API 成本 |
| **DeepSeek Chat** | DeepSeek API | 日常对话 · 快速响应 |
| **DeepSeek Reasoner** | DeepSeek API | 复杂推理 · 数学 · 多步骤规划 |

---

## Agent Platform: OpenClaw

OpenClaw 是本地 Agent 调度平台，负责：

- **多渠道接入**：WhatsApp、终端等统一入口
- **记忆系统**：跨会话持久化上下文（日记 + 长期记忆）
- **心跳巡检**：定时检查邮件 / 日历 / 通知，主动推送
- **多模型路由**：根据任务类型自动选择本地或云端模型

---

## Dev Stack / 开发工具

| 工具 | 用途 |
|------|------|
| **Claude Code** | AI pair programmer，主要开发工具 |
| **Cursor** | AI 辅助 IDE，前端 / 脚本开发 |
| **Ollama** | 本地模型管理与推理服务 |

---

## Why Local? / 为什么跑本地模型

1. **隐私**：敏感数据不出本机
2. **成本**：Qwen3 14B 零 API 费用，适合高频调用场景
3. **低延迟**：局域网内响应，无网络往返
4. **学习**：深入理解模型推理链路和参数调优

---

## Projects Built On This Stack / 基于此环境的项目

- [math-agent](https://github.com/Heliotrope-dev/math-agent) — 数学解题 Agent，Tool Use + SymPy 符号计算

---

*蒋天奇 · 杭州师范大学数学系 · 2026*

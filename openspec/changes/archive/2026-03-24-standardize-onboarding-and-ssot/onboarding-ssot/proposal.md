## Why
现有登舰流程对核心配置文件 (openspec/*.yaml, .gemini/commands/*.toml) 的依赖是隐性的。AI 经常因未读取这些基础“物理属性”而产生推理偏差。我们需要建立分层的“三层读取机制”，将登舰流程标准化为物理指令。

## What Changes
- **三层读取链**: 在 `GEMINI.md` 中硬化 Tier 1 (宪法), Tier 2 (指南), Tier 3 (配置) 的读取顺序。
- **配置即规约**: 强化 `openspec/config*.yaml` 在系统初始化中的地位。
- **入口标准化**: 移除所有分散的初始化引导，全量收口至 `GEMINI.md` 的 [CRITICAL-BOOT-SEQUENCE]。

## Capabilities
- `onboarding-ssot`: 标准化的三层读取登舰协议。

## Impact
- 提升所有 AI Agent 在任何子库 (Workshop) 中的行为一致性。
- 确立了“读取顺序即控制权”的物理标准。

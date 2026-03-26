## Context
当前 `/opsx:propose` 与 `/opsx:apply` 命令执行时，AI Agent 常忽略必要的技能 (writing-plans, executing-plans) 激活，导致执行流“肌肉”缺失。

## Goals
- 实现 `/opsx:propose` 触发时，自动进入 `writing-plans` 的引导流。
- 实现 `/opsx:apply` 触发时，自动进入 `executing-plans` 的执行流。

## Decisions
1. **注入式强制触发**: 通过修改 `.gemini/commands/opsx/*.toml` 的 Prompt 模板，强制注入“当检测到目标任务时，必须先加载关联技能”的硬逻辑。
2. **状态感知校验**: 在 `tasks.md` 的模板中，增加 `Pre-flight Skills` 复选框，强制 AI 在执行前确认状态。

## Trade-offs
- AI 可能会在某些极简变更中觉得“杀鸡用牛刀”，但为了系统确定性，这是必要成本。

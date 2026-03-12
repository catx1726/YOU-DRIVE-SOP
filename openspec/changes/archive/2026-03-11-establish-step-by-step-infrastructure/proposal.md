## Why

当前的 Skill 执行模式是“全量指令集”，当步骤较多或操作复杂时，AI 容易在执行中途因上下文截断或指令优先级漂移而产生错误（如：跳过步骤、路径错误）。本任务旨在引入 `meta-step-runner` 机制，通过 `mode: step-by-step` 元数据和物理进度文件（skill_progress.md），强制 AI 执行“原子化分步”动作，从而极大提高复杂任务的确定性。

## What Changes

- **建立 `meta-step-runner` 技能**：定义如何初始化进度文件、控制任务步进、以及清理临时状态。
- **引入 Frontmatter 标志**：在 Skill 文档中使用 `mode: step-by-step` 显式声明分步模式。
- **物理状态存根**：在 `.gemini/skill_progress.md` 中记录执行进度，防止长对话导致的“失忆”。
- **标准更新**：升级 `workshop-initializing` 和 `foundry-initializing` 为分步模式。

## Capabilities

### New Capabilities
- `meta-step-runner`: 核心控制逻辑，负责分步任务的生命周期管理。

### Modified Capabilities
- `foundry-protocols`: 将 `step-by-step` 模式确立为复杂技能的工业标准。

## Impact
- 提高了初始化、资产收割等核心流程的成功率。
- 实现了 Skill 执行过程的可视化与可中断性。

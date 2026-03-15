## Context

当前文档缺乏一个统一的“上帝视角”。用户往往迷失在具体的命令中，而不理解这些命令在整个智力生产流水线中的位置。
我们需要通过 ASCII 艺术或清晰的分层图表，将 `.gemini/global_standard.md`, `openspec/changes/`, `patterns/` 等目录映射为逻辑上的“实验室”、“引擎”和“资产”。

## Goals / Non-Goals

**Goals:**
- 在 `SOP_CORE_MANUAL.md` 首页建立“SOP 2.0 三层架构”的视觉锚点。
- 将 `GETTING_STARTED.md` 改造为基于角色的操作手册（Role-Based Manual）。
- 确保所有术语（Foundry, Workshop, Distill, Contribute）在文档中定义一致。

**Non-Goals:**
- 修改 AI 的代码逻辑（本次仅限文档重构）。
- 引入新的图表工具（仅使用 Markdown/ASCII）。

## Decisions

- **架构图形式**：采用 Mermaid 或 ASCII Art，优先保证在纯文本环境下的可读性。
- **角色划分**：
    - **Foundry Manager**: 负责维护母库、Skills、Global Standard。
    - **Asset Harvester**: 负责在业务项目中收割资产、反哺母库。

## Risks / Trade-offs

- **[Risk]** 文档重构可能导致旧链接失效 -> **[Mitigation]** 保持文件名不变，仅修改内容结构。
- **[Risk]** 术语定义可能与现有 Skill 描述冲突 -> **[Mitigation]** 仅做定义收敛，不修改 Skill 内部实现，后续通过其他提案修正 Skill。

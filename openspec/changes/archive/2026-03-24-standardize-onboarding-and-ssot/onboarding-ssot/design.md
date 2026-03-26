## Context
目前 AI 进入工作区后，对于“应该先读哪个配置”完全取决于其自发的“探索”。我们需要通过 `GEMINI.md` 的物理结构，将这种探索固定为**强制序列 (Strict Sequence)**。

## Goals
- 建立三层读取链：Tier 1 (宪法) -> Tier 2 (架构/规约) -> Tier 3 (战术配置)。
- 将此序列硬编码为登舰的首要动作。

## Decisions
1. **显式指令序列**: 修改 `GEMINI.md` 中的 `CRITICAL-BOOT-SEQUENCE`，改用数字序号强制 AI 依次读取指定目录。
2. **战术资产挂载**: 在 `Boot Sequence` 中显式添加 `openspec/config*.yaml` 和 `.gemini/commands/*.toml` 的感知步骤。
3. **配置优先级**: 若 Tier 3 配置与 Tier 2 规约冲突，以 Tier 2 (ARCHITECTURE.md) 为准。

## Risks / Trade-offs
- [Risk] AI 启动读取 Token 消耗增大 → [Mitigation] 使用 `read_file` 限制 `start_line` 和 `end_line` 仅读取核心目录摘要。

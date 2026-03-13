## Why

在母库（Foundry）的长期演进中，`openspec/changes/archive/` 根目录下积累了大量涉及“全局规约、元技能重构与架构决策”的任务目录。如果不进行物理分流，将违反 `foundry-protocols/spec.md` 中的“分类存储”门禁，导致资产检索混乱。

## What Changes

- **物理分层**：将位于 `archive/` 根目录下的 13 个历史变更单迁移至 `archive/governance/`。
- **清理根目录**：确保 `archive/` 根下仅保留分类子目录。

## Capabilities

### Modified Capabilities
- `foundry-protocols`: 强化对归档物理分流的执行约束。

## Impact

- 改变了母库历史智力资产的物理分布，提升了资产浓度。
- 不影响现有代码的运行逻辑。

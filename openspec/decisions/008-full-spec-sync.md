# ADR-008: 核心规约资产的完整同步 (Full Synchronization of Core Spec Assets)

## Status
Accepted

## Context
在 SOP 2.0 体系中，OpenSpec 治理依赖于 `schemas/`（定义格式模板）和 `specs/`（定义具体要求）。之前的初始化方案仅同步了 `schemas/`，导致子库虽然具备了协议模板，但无法加载母库定义的 `foundry-protocols` 等实质性“法律”，造成跨库治理失效。

## Decision
1. **同步范围扩大**：更新 `workshop-initializing` 技能，明确要求对齐时必须同时同步母库的 `openspec/schemas/` 和 `openspec/specs/foundry-protocols/`。
2. **感知层对齐**：确保子库的 OpenSpec 环境在初始化后能够立刻感知并加载母库的所有全局规约。
3. **物理路径规范**：母库规约在子库中应保持其原始的 Capability 结构（如 `specs/foundry-protocols/`），以便跨项目的一致性引用。

## Consequences
- **好处**：消除了跨项目治理的“真空地带”；确保了子库生成的每一个 Change 都能自动对齐母库的最高标准。
- **约束**：子库的 `openspec/` 目录将包含母库规约的副本；开发者在子库中修改这些同步过来的规约时应格外谨慎，以免造成本地逻辑与母库标准的冲突。

## Related Sub-Project
N/A

# ADR-013: 生产安全审计与归档分流机制 (Production Safety Audit and Archive Separation)

## Status
Accepted

## Context
随着 SOP 2.0 体系进入准生产状态，AI 执行物理写操作（创建、修改、删除）的安全性变得至关重要。目前的流程中，由于缺乏细粒度的操作审计和物理熔断机制，一旦发生错误操作（如误删、代码冲突），用户难以低成本回溯和恢复。此外，管理层档案（Proposal/Design）与执行层痕迹（Changelog）混杂存储，不利于长期审计。

## Decision
1. **建立安全执行元逻辑**：引入 `meta-safe-executor`，强制在执行所有写操作前进行 Git 快照存盘，并记录语义化 Changelog。
2. **破坏性动作熔断**：针对 `rm`、`mv` 等破坏性指令，AI 必须停止执行并强制请求用户确认（Y/N）。
3. **多级回滚机制**：引入 `meta-rollback`，通过解析 Changelog 提供从语义撤销到精确 Commit 回溯的后悔药能力。
4. **归档物理分流**：
   - 管理档案存放于 `openspec/changes/archive/governance/`。
   - 执行审计日志存放于 `openspec/operations/archive/`。
   - 此决策通过 Patch `openspec-changes-archive` 技能实现。

## Consequences
- **好处**：实现了 AI 操作的“可见、受控、可撤销”；保护了项目资产的物理安全；清晰化了治理与执行的数据边界。
- **约束**：执行写操作时的 Token 和交互成本略有增加；要求项目必须处于 Git 版本控制下。

## Related Sub-Project
N/A (SOP 2.0 Core Infrastructure Safety)

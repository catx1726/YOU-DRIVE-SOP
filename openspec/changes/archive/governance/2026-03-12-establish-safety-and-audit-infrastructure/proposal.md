## Why

目前 AI 执行 Shell 指令（如删除、覆盖、重命名）缺乏物理级的安全熔断与痕迹审计。一旦发生幻觉路径或错误操作，用户难以回溯过程且无法低成本回滚。本任务旨在通过建立 `meta-safe-executor` 和 `meta-rollback` 体系，为 AI 操作注入“事务性”逻辑，实现事前确认、事中存盘、事后审计的工业级安全标准。

## What Changes

- **建立 `meta-safe-executor` 技能**：强制执行写操作前的 Git 自动存盘、语义化 Changelog 记录及危险动作确认。
- **建立 `meta-rollback` 技能**：支持从语义撤销到 Commit ID 精确回溯的多级回滚机制。
- **物理审计隔离**：在母库建立 `openspec/operations/` 目录，专门存放与管理层档案分离的操作级审计日志。
- **更新归档协议**：增强 `openspec-changes-archive`，实现管理档案与执行记录的物理分流归档。

## Capabilities

### New Capabilities
- `meta-safe-executor`: 生产安全执行器，负责实时审计与确认。
- `meta-rollback`: 回滚专家，负责多级撤销与状态恢复。

### Modified Capabilities
- `foundry-protocols`: 将“生产安全审计”确立为 SOP 2.0 强制执行规约。
- `openspec-changes-archive`: 注入操作日志的后置处理钩子。

## Impact
- 显著增强用户对 AI 的信任感。
- 实现了误操作后的“零成本”恢复。
- 建立了工业级的生产审计链。

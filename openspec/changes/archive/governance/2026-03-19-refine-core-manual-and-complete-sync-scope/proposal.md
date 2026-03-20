## Why
`SOP_CORE_MANUAL.md` 作为智力灵魂，目前内容滞后于系统最新的物理硬化动作（如物理安全隔离、混合链路回退）。同时，该文件未被列入子库同步清单，导致子库处于“无架构指导”状态。

## What Changes
- **内容升级**：在手册中增加“物理安全门禁”、“智力继承模式（Linked vs Copied）”及“12.5步闭环执行流”的架构解析。
- **同步补全**：修改 `workshop-initializing` 和 `workshop-sync` 技能，强制物理同步 `SOP_CORE_MANUAL.md`。

## Capabilities
- `foundry-core-manual-alignment`: 确保全链路对核心手册的架构共识。

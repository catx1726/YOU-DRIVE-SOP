## Why

在 SOP 2.0 长期演进中，母库的物理路径可能发生变动，或子库的本地链接可能因磁盘清理、权限变更而失效。目前缺乏一个自动化的、幂等的“刷新与自愈”机制。本任务旨在引入“链接自愈协议”，确保子库可以一键修复、刷新与母库的技能映射。

## What Changes

- **增强 `workshop-initializing` 技能**：注入专门的“链接自愈协议”章节。
- **引入幂等清理机制**：自动识别并清理 `ReparsePoint` (Junction/Symlink) 引用的失效目录。
- **定义触发指令**：为 AI 提供明确的语义触发点，如 "Refresh skills reference from template"。

## Capabilities

### Modified Capabilities
- `foundry-protocols`: 增加关于链路自愈的技术规约。
- `workshop-initializing`: 注入核心自愈逻辑。

## Impact
- 提高了子库链路的鲁棒性。
- 降低了母库技能更新后的手动同步成本。

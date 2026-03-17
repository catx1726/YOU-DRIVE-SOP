## Why
当子库处于 Copied 模式时，无法享受母库规约的实时更新。用户需要一种简单、安全的方式手动“拉取”母库最新的 Skills 和 Patterns，同时不破坏本地已有的业务代码。

## What Changes
- **新增同步技能**：创建 `workshop-sync` 技能，负责从 `link.json` 定义的母库路径增量拉取资产。
- **更新看板**：在 `GEMINI.md` 的快速操作看板中增加“同步母库”指令。
- **冲突保护**：同步过程必须保证子库本地的业务代码（如 `src/`）不被覆盖。

## Capabilities
- `workshop-sync-intel`: 实现子库对母库智力资产的单向物理同步。

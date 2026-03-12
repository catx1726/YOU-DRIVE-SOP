## Context

AI 执行物理操作时的“不确定性”是协作中的最大风险。我们需要在不修改 CLI 源码的前提下，通过技能层注入一套“虚拟事务层”。

## Goals

**1. 建立 `meta-safe-executor` 控制流**
- 触发：所有写操作指令。
- 动作：Git 快照 -> 写入 Changelog -> (如果是破坏性) 弹窗确认 -> 执行。

**2. 建立 `meta-rollback` 能力**
- 模式：语义解析（撤销）+ 历史回溯（Commit）。

**3. 物理审计库建立**
- 路径：`openspec/operations/` 下设 `active` 和 `archive`。

## Decisions

- **Git 消息规范**：使用 `AI_SAFE_SAVE: [Action] <path>` 统一前缀。
- **Changelog 字段**：`Time`, `Action`, `Target`, `Reason`, `Commit_ID`, `Undo_CMD`。
- **归档分流方案**：在 `openspec-changes-archive` 中通过移动 `.gemini/ops_changelog.md` 实现物理分离。

## Risks / Trade-offs

- **[Risk] Git 仓库污染** → [Mitigation] 任务结束后建议用户进行 Squash 或由 AI 自动生成一份干净的最终 Commit。
- **[Risk] 确认弹窗过于频繁** → [Mitigation] 仅针对 `DELETE`, `MOVE`, `OVERWRITE` 开启强制确认，普通 `APPEND` 或 `CREATE` 仅记录不阻塞。

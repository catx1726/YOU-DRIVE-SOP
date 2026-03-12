## MODIFIED Requirements

### Requirement: 环境协议 (env_schema)
环境协议 SHALL 包含生产安全审计项。
- **审计记录**：子库必须维护 `.gemini/ops_changelog.md` 记录所有物理写操作。
- **Git 守卫**：子库必须处于 Git 管理下，且 AI 执行写操作前必须确保当前状态已快照（Commit）。

#### Scenario: 误删恢复
- **WHEN** AI 因幻觉执行了错误的 `rm` 命令。
- **THEN** 用户通过读取 `ops_changelog.md` 中的 `Undo_CMD` 或 Git Commit ID，能够瞬间回滚至破坏性操作前的状态。

### Requirement: 归档门禁 (openspec-changes-archive)
归档流程 SHALL 执行管理档案与执行记录的物理分流。
- **分流存储**：
    - `Proposal/Design` -> `archive/governance/`。
    - `Ops Changelog` -> `archive/operations/`。
- **清理规约**：归档完成后，必须清理子库本地的所有临时操作痕迹。

#### Scenario: 审计分离归档
- **WHEN** 执行 `/opsx:archive`。
- **THEN** 系统自动将 `proposal.md` 等移入管理归档区，同时将 `.gemini/ops_changelog.md` 裁剪并存入操作归档区，保持项目根目录整洁。

## Context

为了让 Skill 的执行过程具备“事务性”和“可回溯性”，我们需要一种基于物理文件的步进协议。

## Goals

**1. 建立 `meta-step-runner` 控制流**
- 触发：检测到 Skill Frontmatter 中的 `mode: step-by-step`。
- 逻辑：Plan -> Write Progress -> Atomic Act -> Wait for User -> Complete -> Cleanup.

**2. 标准化物理状态存根**
- 路径：`.gemini/skill_progress.md`。
- 内容：Skill 名称、任务列表 `[ ]`、当前所在步骤 ID。

## Decisions

- **步进指令**：用户输入 `next`, `continue`, `继续` 触发下一步。
- **强制性读取**：在 `meta-step-runner` 作用期间，每一回合开始 AI 必须显式 `read_file .gemini/skill_progress.md`。
- **失败恢复**：若检测到 `skill_progress.md` 存在但未完成，AI 应主动询问是否“恢复进度（Resume）”。

## Risks / Trade-offs

- **[Risk] 文件遗留**：若 AI 在执行中途崩溃导致文件未清理。 → [Mitigation] 在 `meta-step-runner` 的 Overview 中强调：下次激活任何技能前，若检测到该文件，优先提示清理或恢复。
- **[Risk] 上下文开销**：频繁读取文件。 → [Mitigation] 文件保持极简（< 20 行）。

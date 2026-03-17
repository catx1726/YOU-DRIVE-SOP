## Context
Junction 在 Windows Git 下的清理行为是不确定的。唯一安全的做法是让 Git 完全无视这些路径。

## Decisions
- **前置执行**：在执行 `gemini skills link` 动作前，必须先完成 `.gitignore` 注入。
- **覆盖规则**：
    ```text
    .gemini/skills/
    patterns/
    link.json
    ```
- **物理验证**：写入后，AI 必须执行 `git check-ignore` 验证隔离是否生效。

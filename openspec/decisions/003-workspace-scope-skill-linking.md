# ADR-003: 跨库技能挂载方案 (Cross-Project Skill Linking Strategy)

## Status
Accepted

## Context
在 Windows 环境下，`gemini skills link` 默认会将技能链接至用户全局目录（`C:\Users\HS\.gemini\skills`），这需要创建系统级符号链接（Symlink）。由于默认 shell 权限限制，常导致 `EPERM: operation not permitted` 错误。此外，Gemini CLI 默认仅扫描挂载路径下的一级子目录，多层级目录（如 `superpowers/skills/`）会导致部分技能不可见。

## Decision
1. **技能目录扁平化**：所有核心技能（Superpowers, Init, OpenSpec）均应放置在母库 `.gemini/skills/` 的直接子目录下，禁止深层嵌套。
2. **工作区作用域挂载**：子库连接母库时，强制使用 `--scope workspace` 标志。
3. **自动化确认**：使用 `--consent` 标志跳过安全确认，以支持 AI 自动化流程。

**执行标准命令：**
```powershell
gemini skills link <MOTHER_BASE_PATH>\.gemini\skills --scope workspace --consent
```

## Consequences
- **好处**：解决了 Windows 权限报错问题；实现了技能在子库的即时可见性；母库技能更新可实时同步到所有已挂载的工作区。
- **约束**：子库必须先完成此步骤链接，才能通过 `name` 直接激活母库技能。

## Related Sub-Project
N/A

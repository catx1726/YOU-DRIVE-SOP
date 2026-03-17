## Context
Copied 模式下，子库与母库是松耦合的。同步必须是幂等的且支持增量。

## Goals
- 提供一键同步母库最新技能的功能。
- 仅同步 `.gemini/skills/` 和 `patterns/` 目录。

## Decisions
- **增量拷贝**: 使用 `xcopy /D` (仅拷贝较新文件) 或 `robocopy` 逻辑。
- **路径溯源**: 强制从 `.gemini/link.json` 获取 `foundry_root`。
- **审计记录**: 同步动作必须产生审计日志。

## Risks
- **本地覆盖**: 若用户在子库修改了链接的 Skill，同步会覆盖这些修改。 -> **Mitigation**: 警告用户所有对 `.gemini/skills` 的修改应在母库进行。

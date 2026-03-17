## Context
物理链路是智力继承的基础。复制虽然能保证技能可用，但破坏了资产的实时流动。

## Goals
- 优先建立物理 Junction 映射。
- 在失败时通过物理复制确保任务不中断。
- 保证用户对链路状态的物理透明度。

## Decisions
- **优先 Junction**: 使用 `gemini skills link --consent`。
- **降级 Copy**: 若探测到 `.gemini/skills` 属性非 `ReparsePoint`，执行全量拷贝。
- **状态持久化**: 在 `link.json` 中记录 `link_type`: `"junction" | "copy"`。

## Risks
- **双向修改冲突**: 在复制模式下，子库修改 Skill 不会反映到母库，容易导致版本代沟。

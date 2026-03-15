## Why

母库（Foundry）在初始化时如果生成的配置文件不完整，会导致下游子库（Workshop）在同步时缺失关键的 context、rules 和 tasks 模板。这直接造成了子库 AI 缺乏执行规约约束。

## What Changes

- **配置种子补完**：修改 `foundry-initializing` 技能，强制生成一个包含 `context`, `rules`, `templates` 的完整版 `config_foundry.yaml`。
- **模板标准化**：确保生成的模板包含“任务 0：规约自检”的物理定义。
- **自愈逻辑**：若母库配置缺失，初始化技能应主动修复而非仅报错。

## Capabilities

### New Capabilities
- `foundry-config-seeding`: 负责生成工业级的母库配置种子。

### Modified Capabilities
- `foundry-bootstrapping`: 强化对配置文件的物理生成能力。

## Impact

- 修改 `.gemini/skills/foundry-initializing/SKILL.md`。
- 影响母库 `openspec/config_foundry.yaml` 的默认产出内容。

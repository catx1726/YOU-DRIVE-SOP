## Why

虽然 `global_standard.md` 定义了收割意识，但目前 AI 缺乏具体的操作协议来执行从业务代码到“母库 Pattern”和“通用 Skill”的转化。这导致收割过程随意、格式不一，且难以在母库中被再次检索利用。本任务旨在通过建立 `asset-harvesting` 技能和标准化资产布局，实现工业级的资产提纯。

## What Changes

- **建立 `asset-harvesting` 技能**：定义如何跨库提取逻辑、参数化去业务化以及生成配套测试。
- **标准化 `patterns/` 布局**：强制执行“代码+测试+说明”三件套模式。
- **标准化 `skills/` 提纯逻辑**：定义如何将代码背后的工程经验转化为通用的 Skill 文档。
- **闭环集成**：将收割动作强制集成到 `/opsx:archive` 归档门禁中。

## Capabilities

### New Capabilities
- `asset-harvesting`: 专门负责逻辑提取、参数化处理和跨库写入母库的技能。

### Modified Capabilities
- `foundry-protocols`: 更新 `logic_schema`，固化资产存储的物理目录标准。
- `openspec-changes-archive`: 增强归档门禁，在归档前强制触发资产提纯检查。

## Impact
- 实现了开发产物向母库智力资产的自动转化。
- 提高了母库 `patterns/` 的可复用性和工业纯度。

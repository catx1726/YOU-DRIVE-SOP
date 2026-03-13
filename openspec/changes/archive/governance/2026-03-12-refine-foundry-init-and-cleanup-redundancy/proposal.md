## Why

目前 `foundry-initializing` 技能仅执行了“物理建档”动作，导致生成的全局标准与协议模板内容缺失（空文件），造成用户冷启动困惑。同时，原有的 `meta/` 和 `common/` 物理目录在技能扁平化决策后已失去实用价值，成为冗余实体。本任务旨在通过“模板内容同步”和“结构极简清理”，实现母库初始化的即插即用和全量规约继承。

## What Changes

- **增强 `foundry-initializing` 技能**：
    - 将“创建空文件”变更为“注入预置模板内容”。
    - 内置 `.gemini/global_standard.md` 的中文宪法文案。
    - 内置 `openspec/schemas/` 的工业级协议模板。
- **物理结构清理**：从初始化流程中彻底移除 `meta/` 和 `common/` 目录的创建逻辑。
- **术语同步**：在所有初始化产物中统一使用 `YOU-DRIVE-SOP` 品牌术语。

## Capabilities

### Modified Capabilities
- `foundry-initializing`: 职责从“安装器”升级为“规约生效器”。
- `foundry-protocols`: 更新物理结构规约，正式废弃嵌套技能目录。

## Impact
- 新用户在初始化后将立即获得完整的 SOP 执行流环境。
- 母库目录结构变得更加扁平且符合 CLI 加载逻辑。

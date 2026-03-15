## Why

当前子库初始化流程存在严重缺陷：
1. **规约失联**：子库无法同步母库 `openspec/specs/` 下的核心治理规约，导致子库 AI 无法继承“自动化”与“血统”逻辑。
2. **引导模糊**：缺乏初始化后的物理验证与流程进度感知。
3. **脆弱的母库**：母库缺乏自动补全核心规约的能力，增加了新实验室的搭建门槛。

## What Changes

- **全量同步机制**：修改 `workshop-initializing` 技能，实现母库 `openspec/` 目录的全量物理同步（包含 specs, schemas, protocols）。
- **初始化闭环报告**：初始化完成后自动执行一次全量物理自检，并输出规约对齐清单。
- **模板自动填充**：修改 `foundry-initializing` 技能，使其能自动生成缺失的 `vcs-lifecycle-automation` 等核心规约模板。
- **状态感知增强**：在子库 `GEMINI.md` 中注入动态状态检查指令。

## Capabilities

### New Capabilities
- `foundry-bootstrapping`: 负责母库核心规约模板的物理生成与对齐。
- `workshop-full-alignment`: 负责子库与母库规约的全量物理同步与验证。

### Modified Capabilities
- `foundry-protocols`: 增加对“全量同步”路径的物理定义。

## Impact

- 影响 `workshop-initializing` 和 `foundry-initializing` 两个核心技能。
- 修改子库初始化后的 `GEMINI.md` 生成逻辑。
- 增强母库 `openspec/schemas/` 的完整性。

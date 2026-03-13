## Why

目前子库在通过 `workshop-initializing` 对齐后，缺乏直观的交互线索引导用户执行下一步。新用户（驾驶员）往往在初始化成功后陷入“不知道该输入什么指令”的困境。本任务旨在通过自动生成“指令看板式”的 `GEMINI.md`，并在初始化流程末尾引入“交互式选择引导”，实现从“环境就绪”到“实战驱动”的无缝衔接。

## What Changes

- **重塑子库 `GEMINI.md` 模板**：
    - 增加「🚀 快速操作看板」章节。
    - 列出针对 Legacy 和 Feature 场景的核心指令。
- **增强 `workshop-initializing` 交互**：
    - 在流程末尾增加“下一步动作”的选择引导。
    - 实现对用户意图的即时响应（A/B 路径分流演示）。

## Capabilities

### Modified Capabilities
- `workshop-initializing`: 注入交互引导逻辑。
- `foundry-protocols`: 将“用户交互引导”确立为子库对齐的质量标准。

## Impact
- 显著降低了 YOU-DRIVE-SOP 的认知门槛。
- 提高了框架在多协作场景下的确定性与亲和力。

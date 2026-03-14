## Why

在之前的“大规模治理资产重整”任务中发现，虽然我们执行了物理迁移，但相关的规约文档（Spec）并未同步更新。这种“图纸与建筑脱节”的情况违反了 SOP 2.0 的一致性原则。我们需要通过多 Agent 协同，同步更新全局规约与手册，将“治理类物理分流”正式固化为系统性行为。

## What Changes

- **规约升级**：在 `openspec/specs/foundry-protocols/spec.md` 中增加关于治理类资产强制分流的 Requirement。
- **手册对齐**：在 `SOP_CORE_MANUAL.md` 的归档章节中补充物理路径校验的详细说明。
- **流程验证**：确保新生成的规约能正确引导未来的归档动作。

## Capabilities

### Modified Capabilities
- `foundry-protocols`: 注入治理资产物理分流的硬性约束。
- `governance-manual`: 完善归档逻辑的文档描述。

## Impact

- 彻底消除了归档时“该存哪”的决策模糊。
- 实现了母库历史智力资产的自动分类对齐。
- 演示了多 Agent 在复杂规约同步场景下的协作能力。

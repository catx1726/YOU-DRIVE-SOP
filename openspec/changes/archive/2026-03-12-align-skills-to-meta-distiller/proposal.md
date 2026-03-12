## Why

随着 `meta-distiller` (ADR-011) 的确立，现有的 `legacy-extractor`、`workshop-initializing` 等技能中关于资产提取的旧描述已变得过时且存在路径冲突。如果不进行统一对齐，AI 在执行不同任务时会产生行为不一致（如：有时写进 logic.md，有时写进 patterns/）。本任务旨在清理全库冗余逻辑，将所有提纯行为导向 `meta-distiller` 标准。

## What Changes

- **重构 `legacy-extractor`**：废弃直接写入 `logic.md` 的模式，改为调用 `meta-distiller` 并写入 `distill_stage`。
- **更新 `workshop-initializing`**：明确收割流程的工具链依赖。
- **更新 `global_standard.md`**：修正旧的技能名称引用。
- **更新 `writing-skills`**：建立与 `meta-distiller` 的跨技能引用关系。

## Capabilities

### Modified Capabilities
- `foundry-protocols`: 强化“提纯权威性”规约。
- `legacy-extractor`: 重大行为变更。
- `workshop-initializing`: 流程对齐。

## Impact
- 实现了全库技能在“资产收割”动作上的高度一致。
- 彻底消除了子库资产反哺时的路径歧义。

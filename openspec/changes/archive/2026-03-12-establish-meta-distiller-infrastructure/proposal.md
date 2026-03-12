## Why

目前的资产提纯流程存在动作不规范、缺乏中间审批、且未能实现“能力（Skill）与图纸（Pattern）”深度缝合的问题。本任务旨在建立 `meta-distiller` 元技能，通过引入子库暂存区（Staging）和三层闭环标准，确保所有归档资产都具备工业级的纯净度和可索引性。

## What Changes

- **建立 `meta-distiller` 技能**：取代并重构 `asset-harvesting`，定义核心提纯协议。
- **引入 Staging 机制**：在子库建立 `.gemini/distill_stage/`，实现“提纯-审核-入库”的解耦。
- **确立三层标准**：
    - **Skill 层**：负责场景触发与轻量契约（common-xxx.md）。
    - **Pattern 层**：负责物理实现与测试验证（index三件套）。
    - **Audit 层**：归档时的自动合并门禁。
- **闭环集成**：更新 `openspec-changes-archive`，增加对 Staging 资产的合并提醒。

## Capabilities

### New Capabilities
- `meta-distiller`: 资产提纯的元控制引擎。

### Modified Capabilities
- `foundry-protocols`: 升级逻辑提纯规约，固化 Staging 与 Skill-Pattern 联动标准。
- `openspec-changes-archive`: 注入 Staging 资产识别与合并逻辑。

## Impact
- 实现了母库资产的“受控演进”。
- 极大降低了 AI 检索和复用母库代码的认知负担。

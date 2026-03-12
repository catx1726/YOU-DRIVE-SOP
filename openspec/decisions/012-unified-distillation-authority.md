# ADR-012: 统一资产提纯权威 (Unified Distillation Authority)

## Status
Accepted

## Context
随着 `meta-distiller` (ADR-011) 的引入，系统具备了工业级的资产收割能力。然而，现有的 `legacy-extractor`、`workshop-initializing` 等技能中仍残留着旧的、冲突的资产提取逻辑（如直接写入 `logic.md` 或 `asset-harvesting` 名称）。这种逻辑冗余会导致 AI 在不同场景下的提纯动作不一致，严重影响母库资产的质量与统一性。

## Decision
1. **确立唯一执行引擎**：全库所有的“资产提纯”、“逻辑收割”动作必须统一通过 `meta-distiller` 执行。
2. **重构 legacy-extractor**：将其定位从“逻辑记录员”转变为“资产猎头”。移除其代码写入逻辑，改为通过分步流程引导用户激活 `meta-distiller`。
3. **废弃本地代码堆积**：正式废止在子库 `openspec/specs/logic.md` 中存储具体代码实现的模式，确保所有经过验证的逻辑唯一流向母库 `patterns/`。
4. **全库术语对齐**：Patch 全局标准、初始化技能及相关规约，彻底清除对旧名称 `asset-harvesting` 的引用。

## Consequences
- **好处**：实现了全库“政令统一”，确保所有收割资产均符合“三件套”和“Staging”标准；简化了技能维护。
- **约束**：跨技能协作增多，要求 AI 具备更强的技能链激活意识；用户需适应“发现资产 -> 触发提纯”的二段式操作。

## Related Sub-Project
N/A (SOP 2.0 Governance Simplification)

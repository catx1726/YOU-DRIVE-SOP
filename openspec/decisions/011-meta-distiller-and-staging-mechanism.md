# ADR-011: 提纯专家元技能与暂存审核机制 (Meta Distiller and Staging Mechanism)

## Status
Accepted

## Context
在 SOP 2.0 体系中，资产的跨库“反哺”是自演进的核心。然而，直接将子库提纯的代码写入母库存在高风险：可能引入不纯净的业务逻辑，或者因路径错误导致母库混乱。此外，当前的 Skill 与 Pattern 之间缺乏显式的物理引用关系，导致“知识”与“实现”脱节。

## Decision
1. **建立 meta-distiller 元技能**：取代旧有的 `asset-harvesting`，作为资产提纯的唯一权威逻辑。
2. **引入子库暂存区 (Staging)**：所有提纯资产必须首先在子库根目录的 `.gemini/distill_stage/` 生成，供用户进行最终审批。
3. **Skill-Pattern 联动引用**：强制要求生成的 `common-` 技能文档中包含指向对应 `patterns/` 物理文件的 Markdown 硬链接。
4. **归档自动化合并**：将暂存资产的检测与合并询问集成到 `/opsx:archive` 流程中，实现“任务结束即资产入库”的闭环。

## Consequences
- **好处**：实现了母库演进的“受控性”和“高质量”；确立了资产收割的工业级流水线；加强了 Skill 系统的可发现性与可操作性。
- **约束**：归档动作前增加了自动化的提纯审计环节；要求 AI 具备跨库文件操作的精准控制力。

## Related Sub-Project
N/A (SOP 2.0 Core Infrastructure Refinement)

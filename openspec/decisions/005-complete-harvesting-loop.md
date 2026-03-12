# ADR-005: 资产收割闭环与标准化 (Asset Harvesting Loop & Standardization)

## Status
Accepted

## Context
在 SOP 2.0 体系中，资产的“提纯”与“反哺”是核心价值所在。虽然 `global_standard.md` 提出了收割门禁，但缺乏具体的操作规约和物理存储标准。这导致收割过程难以量化，且产出的资产（Patterns & Skills）格式混乱，难以复用。

## Decision
1. **建立 asset-harvesting 技能**：专门负责跨库执行逻辑提取、参数化去业务化、以及母库目录的物理写入。
2. **Patterns 标准化**：存入 `patterns/` 的资产强制执行“三件套”布局（`index.ts`, `index.test.ts`, `README.md`），确保 Node 20 兼容。
3. **Skills 自动化生成**：每个 Pattern 必须在母库 `skills/` 根级同步生成一份 `common-<name>.md` 指令文件，以便未来 AI 能够通过名称直接调用。
4. **归档强制门禁**：在 `openspec-changes-archive` 中注入强制钩子，归档前必须执行资产提纯反思并提交《收割报告》。

## Consequences
- **好处**：实现了从业务代码到智力资产的自动化生产线；确保了母库资产的高质量和高度可索引性；形成了完整的“开发-提纯-复用”闭环。
- **约束**：归档流程将略微变长（增加了提纯环节）；要求开发者具备更高的“解耦”意识。

## Related Sub-Project
N/A (Core SOP 2.0 Loop Refinement)

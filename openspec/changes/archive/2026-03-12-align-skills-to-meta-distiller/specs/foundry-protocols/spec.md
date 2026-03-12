## MODIFIED Requirements

### Requirement: 逻辑提纯协议 (logic_schema)
逻辑提纯 SHALL 具备全局唯一入口。
- **唯一性**：母库体系内所有的资产收割、逻辑提炼动作必须由 `meta-distiller` 技能统一执行。
- **废弃项**：废弃在子库 `openspec/specs/logic.md` 中存储具体实现代码的做法。该文件仅用于记录逻辑描述，不作为代码资产的载体。
- **目标对齐**：提纯资产的唯一终点为母库 `patterns/`（物理代码）和 `skills/`（逻辑能力）。

#### Scenario: 从旧项目逆向收割
- **WHEN** AI 使用 `legacy-extractor` 识别出一段高价值业务代码。
- **THEN** AI 禁止在本地 `logic.md` 中展开代码，而是引导用户激活 `meta-distiller` 将该资产反哺至母库。

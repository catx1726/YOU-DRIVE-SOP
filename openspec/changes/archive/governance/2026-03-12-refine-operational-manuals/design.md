## Context

为了提升 `YOU-DRIVE-SOP` 的开源成熟度，我们需要解决“说明书不够具体”和“技能内容不够深厚”的问题。

## Goals

**1. 手册分流 (Scenario-Driven Manuals)**
- 在 README 和 GETTING_STARTED 中，为“旧项目”和“新功能”提供各自独立的指令流向导。

**2. 建立高浓度技能标准 (High-Density Skill Standard)**
- 采用 `step-by-step` 模式进行技能编写。
- 强制包含：Overview, Boundaries, The Stance, Step-by-Step Workflow, Patterns & Anti-Patterns, Final Audit。

## Decisions

- **手册结构**：
    - **[场景 A] 旧项目逆向**：`activate_skill workshop-initializing` -> `legacy-extractor` -> `meta-distiller` -> `archive`。
    - **[场景 B] 新功能开发**：`/opsx:propose` -> `brainstorming` -> `/opsx:apply` -> `TDD` -> `meta-distiller` -> `archive`。
- **技能重构模式**：
    - 废弃“一次性生成几百行”的模式。
    - 采用“分回合对话生成”：AI 每回合只提交一个章节，待用户审核逻辑严密度后再写下一章。

## Risks / Trade-offs

- **[Risk] 学习成本增加** → [Mitigation] 手册中增加“快速起步”极简路径，详细逻辑放在“深入探索”章节。
- **[Risk] 内容冗余** → [Mitigation] 严格执行 `writing-skills` 的 Token 经济学，确保每一句话都是干货。

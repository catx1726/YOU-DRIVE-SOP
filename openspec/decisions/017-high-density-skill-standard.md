# ADR-017: 高浓度技能编写标准与分步增长规约 (High-Density Skill Standard and Staged Growth)

## Status
Accepted

## Context
随着 YOU-DRIVE-SOP 体系的复杂度增加，传统的“一次性生成”技能文档模式暴露出了细节单薄、逻辑不够严密以及无法应对模型输出上限的问题。为了提升框架的工业级质感，确保每一项沉淀的技能都能提供全视角的思维指导，我们需要一套更高标准的内容生产协议。

## Decision
1. **确立五维章节标准**：所有复杂元技能必须包含以下核心章节：
    - **Boundaries (边界)**：定义非适用场景与前置依赖。
    - **The Stance (姿态)**：定义 AI 执行时的思维模式与原则（如逻辑审计员）。
    - **Step-by-Step Workflow**：原子化、带任务存根的执行流。
    - **Patterns & Anti-Patterns**：提供正反面工程案例对比。
    - **Final Audit**：定义产物质量自检清单。
2. **强制分步增长模式**：在创建或重构技能时，禁止全量输出。必须按章节分回合提交，每回合经由人工审核逻辑严密度后再推进至下一章节。
3. **元数据集成**：利用 `mode: step-by-step` 标志位触发 `meta-step-runner` 控制引擎。

## Consequences
- **好处**：极大地提升了 Skill 文档的逻辑深度与实战参考价值；解决了长文档生成时的 Token 截断与缩水问题；实现了对 AI 思维姿态的标准化约束。
- **约束**：技能编写过程需要更多的人机协作回合；要求开发者具备更强的工程抽象能力。

## Related Sub-Project
N/A (SOP 2.0 Content & Quality Standard)

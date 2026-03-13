## MODIFIED Requirements

### Requirement: 技能文档规约 (writing-skills)
技能编写 SHALL 追求高浓度、严逻辑与全视角。
- **结构化强制**：复杂技能必须包含：
    - **Boundaries (边界)**：明确说明该技能“不解决什么”以及“执行前置条件”。
    - **The Stance (姿态)**：定义 AI 执行时的思维模式（如：严谨的审计员、好奇的探索者）。
    - **Step-by-Step Workflow**：带有进度存根的任务列表。
    - **Patterns & Anti-Patterns**：提供具体的正反面案例对比。
    - **Final Audit**：定义产物自检项。
- **分步生成**：技能的创建与重构必须遵循“步进增长”模式，每章节需经人工审核逻辑。

### Requirement: 文档亲和力 (Documentation Affinity)
操作手册 SHALL 具备场景感知能力。
- **路径分流**：README 必须清晰划分“Legacy (旧项目)”与“Feature (新功能)”两条核心操作链路。
- **指令可视化**：手册中必须展示完整的指令链示例（Instruction Chains）。

#### Scenario: 构建高浓度元技能
- **WHEN** AI 编写一个新的元技能（如 `meta-distiller`）。
- **THEN** AI 不再直接输出全文，而是先定义姿态与边界，在获得用户对逻辑严密性的认可后，再分步细化后续章节。

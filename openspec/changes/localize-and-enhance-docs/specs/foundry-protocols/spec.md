## ADDED Requirements

### Requirement: 文档亲和力 (Documentation Affinity)
开源文档 SHALL 兼顾国际化展示与本地化深度。
- **中文优先**：在针对中文用户的分发版本或主仓库中，核心逻辑说明必须包含准确的中文翻译。
- **术语对照**：文档必须提供关键工程术语的对照表（如：Distillation -> 提纯）。

### Requirement: 工具链透传 (Toolchain Disclosure)
README 与入门指南 SHALL 完整覆盖核心工具的操作逻辑。
- **OpenSpec 指引**：必须解释 Propose -> Apply -> Archive 的状态流转。
- **Superpowers 指引**：必须解释 Skill 的激活方式（activate_skill）及 TDD 强制要求。

#### Scenario: 新手快速驱动
- **WHEN** 用户首次打开 README。
- **THEN** 用户能通过文档快速区分“什么是治理（OpenSpec）”和“什么是执行（Superpowers）”，并能找到第一条该输入的指令。

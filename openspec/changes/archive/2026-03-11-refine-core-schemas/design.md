## Context

SOP 2.0 实验室（Wuhan-Lab）需要一套标准的规约模板，以指导子库的对齐和资产的收割。目前，母库已有物理结构和全局标准，但缺乏具体的、可由机器验证的 Schema 文件。

## Goals / Non-Goals

**Goals:**
- 定义 `env_schema.md`：规范环境扫描项（Node, npm, Engines, Critical Deps）。
- 定义 `logic_schema.md`：规范资产提取契约（Input/Output, Decoupling Rules, Parameterization）。
- 定义 `decision_schema.md`：规范架构决策记录格式（Status, Context, Decision, Consequences）。
- 确保这些 Schema 能够直接被 `workshop-initializing` 和后续的收割工具读取。

**Non-Goals:**
- 本任务不涉及具体的代码自动化收割脚本（Scrapers）开发。
- 不涉及母库以外的第三方库管理。

## Decisions

- **Schema 格式选择**：采用 Markdown 结构化文档。理由：Markdown 兼具人类可读性和机器可解析性（通过正则表达式或 AST），且符合 `writing-skills` 的文档驱动风格。
- **强制 Node 20 校验**：在 `env_schema` 中将 Node 20 设为基准。理由：为了保证收割后的资产在母库环境中具备最高的兼容性和现代特性。
- **去业务化占位符标准**：在 `logic_schema` 中定义 `{{PROJECT_NAME}}`, `{{VAR_NAME}}` 等标准占位符格式。

## Risks / Trade-offs

- **[Risk] 子库环境过旧** → [Mitigation] 在 `env_schema` 中增加“代沟评估（Gap Analysis）”字段，显式记录转换成本。
- **[Risk] 逻辑提取过度碎片化** → [Mitigation] `logic_schema` 要求每个提取的 Pattern 必须具备功能完整性（即：逻辑闭环）。

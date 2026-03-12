# ADR-015: 本地化与教育型文档增强 (Localized and Educational Documentation Enhancement)

## Status
Accepted

## Context
随着 `YOU-DRIVE-SOP` 向开源转型，文档的国际化调性固然重要，但对于核心中文开发者群体，高质量的母语说明是降低认知成本的关键。此外，`OpenSpec` (治理) 与 `Superpowers` (执行) 作为框架的两大支柱，其分工逻辑对新用户来说相对抽象。我们需要通过语言回正和“工具链手册”注入，实现对驾驶员的深度赋能。

## Decision
1. **核心文档汉化**：将 `global_standard.md`、`README.md` 等核心文件恢复为高质量中文，保持专业术语的双语对照。
2. **注入工具链手册**：在 `README` 中显式开辟章节，解释 `OpenSpec` 的任务流（Propose/Apply/Archive）与 `Superpowers` 的专家技能（Skills/TDD）如何协作。
3. **指令实例化**：在 `GETTING_STARTED` 中提供贯穿开发全生命周期的具体指令示例，实现“所见即所得”的教学效果。
4. **安全合规实施**：本任务的全程汉化与增强动作均通过 `meta-safe-executor` 进行审计记录。

## Consequences
- **好处**：极大地降低了中文用户的上手门槛；清晰化了治理与执行的边界；增强了项目的易用性与社区亲和力。
- **约束**：在后续更新中需要同步维护中英双语或确保中文翻译的实时性。

## Related Sub-Project
N/A (SOP 2.0 UX & Education Refinement)

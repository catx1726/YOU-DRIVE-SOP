# Gemini-Superpowers 最佳实践简报 (Execution Upstream Audit)

## 1. 协作模式：子智能体隔离
- **三段式审计**：Implementer -> Spec Reviewer -> Quality Reviewer。
- **[集成建议]**：在 `meta-distiller` 中引入“虚拟审计员”角色，将代码纯度检查与逻辑实现解耦。

## 2. 纪律约束：根因铁律
- **Iron Law**：严禁在未理解根因前执行 Patch。
- **[集成建议]**：将此铁律写入 `global_standard.md`，作为所有开发任务的前置门禁。

## 3. 文档质感：可视化逻辑
- **Dot Flowcharts**：使用 Graphviz 描述决策树和执行流。
- **[集成建议]**：在 `ADR-017`（高浓度技能标准）中，将“逻辑流程图”列为复杂技能的必须章节。

## 4. 压力测试场景
- **Anti-Hallucination**：Skill 包含大量的“Red Flags”和“Common Rationalizations”（常见借口）。
- **[集成建议]**：我们的元技能应补齐“AI 常见借口对照表”，通过显式否定来封堵 AI 的偷懒路径。

## Context

在 `foundry-protocols` 的初版规格中，使用了“Canvas 渲染逻辑”这种特定业务案例。根据 SOP 2.0 的通用性原则，母库规约应避免具体业务假设。

## Goals / Non-Goals

**Goals:**
- 将 `foundry-protocols` 中的特定案例替换为通用场景描述。
- 确保规格的机器可测试性不受影响。

**Non-Goals:**
- 不涉及对 `logic_schema.md` 本身的物理文件内容修改（该文件已是去业务化的）。
- 不涉及新的功能性规约添加。

## Decisions

- **替换策略**：将 `Canvas 渲染逻辑` 统一替换为 `去业务化后的业务模块 (Decoupled Business Module)` 或 `通用数据转换钩子 (General Data Hook)`。
- **保留结构**：维持原有的 `Requirement` 和 `Scenario` 结构，仅微调描述文字。

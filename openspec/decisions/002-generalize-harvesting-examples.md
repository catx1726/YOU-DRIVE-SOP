# ADR-002: 母库规约的去业务化修正 (Generalization of Spec Examples)

## Status
Accepted

## Context
在 `foundry-protocols` (ADR-001) 的初版规格中，由于对初始化语境的误读，错误地将“Canvas 渲染逻辑”作为资产提取的具象化案例。这种特定的业务假设（Business Bias）不仅容易引发 AI 的幻觉，也违背了母库作为“中央实验室”应具备的通用性规约标准。

## Decision
1. **移除具体业务场景**：将主规约 `foundry-protocols` 中的所有“Canvas”相关描述替换为通用术语“去业务化的业务处理模块（Decoupled Business Module）”。
2. **强制通用化审查**：在后续所有的 Specs 编写中，Scenario 必须优先使用通用技术术语，仅在 `supporting-file` 或 `examples/` 中提供特定的行业案例。

## Consequences
- **好处**：消除了 AI 在执行资产收割任务时的潜在偏见，确保了规约对所有类型的逻辑（Canvas, API, Utils）具备同等的指导效力。
- **约束**：在编写 Specs 时需进行额外的“纯净度检查”，避免引入当前子项目的特定词汇。

## Related Sub-Project
N/A

## Why

在 `foundry-protocols` 规格的初版中，由于上下文误读，我将“Canvas 渲染逻辑”作为资产提取的具象化案例。这种具体业务假设偏离了母库规约的通用性原则（Generalization Principle）。本任务旨在将所有特定的业务描述替换为通用的逻辑描述，确保规约的纯净度。

## What Changes

- **修正资产提取场景**：将 `Canvas 渲染逻辑` 替换为 `通用业务处理函数 (General Business Function)` 或 `数据转换钩子 (Data Transformation Hook)`。
- **强化去业务化定义**：在 `logic_schema` 的场景描述中，强调逻辑提取的通用性和参数化标准，不带任何特定业务色彩。

## Capabilities

### New Capabilities
- N/A

### Modified Capabilities
- `foundry-protocols`: 修正资产收割场景的具体描述，使其更具普适性。

## Impact
- 仅影响 `openspec/specs/foundry-protocols/spec.md` 的内容描述。
- 提高了母库作为“实验室”的架构纯洁度。

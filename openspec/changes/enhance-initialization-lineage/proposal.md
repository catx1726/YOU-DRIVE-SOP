## Why

目前母库（Foundry）与子库（Workshop）的初始化逻辑缺乏深度的“智力溯源”：
1. **母库端**：AI 虽然知道基于 OpenSpec 和 Superpowers，但不会主动阅读 `tools/` 目录下的源码，导致对最新上游特性的理解可能滞后。
2. **子库端**：初始化完成后，AI 无法自动继承母库已对齐的 SOP 2.0 规约，导致智力链条断裂。

我们需要建立“源码级对齐（母库）”与“契约级对齐（子库）”的继承模型。

## What Changes

- **母库初始化 (`foundry-initializing`)**：增加 `Step 0` 强制 AI 深度阅读 `tools/` 下的上游源码与 Schemas。
- **子库初始化 (`workshop-initializing`)**：增加 `Step 5` 强制 AI 读取母库的 `SOP_CORE_MANUAL.md`。
- **手册优化**：在 `SOP_CORE_MANUAL.md` 中增加“智力握手协议”锚点。

## Capabilities

### Modified Capabilities
- `foundry-protocols`: 强化“智力溯源”与“规约继承”的技术要求。
- `workshop-initializing`: 注入核心的手册对齐逻辑。

## Impact

- 确保了母库作为智力源头的数据新鲜度。
- 实现了子库与母库规约的“零成本”同步。
- 降低了多仓库管理下的 AI 幻觉率。

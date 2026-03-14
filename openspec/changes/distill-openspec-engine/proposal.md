## Why

虽然母库已物理集成了上游 OpenSpec 引擎，但对其底层实现（如工件生成算法、分枝联动机制、归档物理逻辑）的理解目前仅存在于 AI 的临时内存中。为了实现 SOP 2.0 的“物理化”目标，我们需要将这些核心逻辑提炼为项目规约，确保母库拥有自主解释能力。

## What Changes

- **新建规约目录**：创建 `openspec/specs/upstream-lineage/`。
- **源码全量通读（Phase 1）**：通读 `tools/OpenSpec/src/` 目录下的核心逻辑代码。
- **逻辑物理化**：在 `openspec/specs/upstream-lineage/openspec-core.md` 中记录解构心得。

## Capabilities

### New Capabilities
- `upstream-mechanics-alignment`: 定义如何对齐并文档化上游引擎的核心逻辑。

## Impact

- 提升了母库对 OpenSpec 故障的诊断能力。
- 为后续自定义 Schema 开发提供了物理参考。
- 彻底消除了对上游工具的“使用幻觉”。

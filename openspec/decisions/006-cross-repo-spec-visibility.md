# ADR-006: 跨库链路持久化与规约可见性 (Cross-Repo Link Stub & Spec Visibility)

## Status
Accepted

## Context
在 SOP 2.0 体系中，子库（Workshop）需要能够被非 CLI 工具（如自定义脚本或其他 AI 代理）识别其所属母库。此外，由于 OpenSpec 工具默认仅扫描当前目录的 Specs，子库在初始化后无法自动加载母库的“立法”规约，导致规约检查失效。

## Decision
1. **建立物理链路存根**：在子库执行 `workshop-initializing` 时，强制创建 `.gemini/link.json` 文件，记录母库的绝对路径。
2. **规约影子同步**：初始化流程中增加规约同步步骤，将母库 `openspec/schemas/` 下的协议同步或引用至子库 `openspec/schemas/foundry/` 目录。
3. **保持逻辑一致性**：更新技能文档与主规格说明，确保初始化动作包含上述两个物理层面的增强。

## Consequences
- **好处**：实现了跨工具的链路感知；确保了子库在开发过程中始终具备规约约束力；消除了 AI 在子库中的“知识盲区”。
- **约束**：子库目录结构将增加 `schemas/foundry/` 深度；同步动作需保证单向性（母库 -> 子库），防止子库污染母库协议。

## Related Sub-Project
N/A (SOP 2.0 Infrastructure Alignment)

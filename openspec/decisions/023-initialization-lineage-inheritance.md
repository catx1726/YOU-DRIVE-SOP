# ADR 023: 双端初始化智力继承模型

## 状态 (Status)
已通过 (Accepted)

## 上下文 (Context)
随着上游工具（OpenSpec, Superpowers）的频繁更新，AI 引擎仅凭通用模型常识已不足以应对物理仓库中的特定逻辑。同时，子库（Workshop）在初始化后往往处于“智力孤岛”状态，无法感知母库已沉淀的规约精髓。

## 决策 (Decision)
1.  **母库深度溯源**：在 `foundry-initializing` 中强制加入 `Step 0: Upstream Deep-Dive`。AI 必须物理阅读 `tools/` 目录下的上游源码与 Schemas，确保智力源头的实时性。
2.  **子库契约继承**：在 `workshop-initializing` 中强制加入 `Step 5: Foundry Manual Alignment`。子库 AI 必须通过读取母库的 `SOP_CORE_MANUAL.md` 来继承全套 SOP 2.0 规约。
3.  **分层对齐架构**：确立“源码对齐（母库） -> 手册对齐（子库）”的级联继承模型。

## 后果 (Consequences)
- **正面**：确保了跨仓库、跨助理的规约一致性；显著降低了母库升级后的子库同步成本。
- **负面**：初始化过程增加了少量的物理读取动作，但在智力准确度面前，这种 Token 损耗是必要的投资。

---
*Created on 2026-03-13 by YOU-DRIVE-SOP Engine.*

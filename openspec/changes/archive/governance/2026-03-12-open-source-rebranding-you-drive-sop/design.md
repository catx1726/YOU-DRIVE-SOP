## Context

我们要把这套系统的重心从“我写好了给你用”转向“你驱动它为你自己服务”。

## Goals

**1. 品牌重塑 (Rebranding)**
- 名称：`YOU-DRIVE-SOP`。
- 调性：极客、掌控、自主演进。

**2. 路径抽象 (Abstraction)**
- 废弃所有 `D:\` 开头的硬编码。
- 引入 `{{FOUNDRY_ROOT}}` 全局上下文变量。

## Decisions

- **README 风格**：采用简洁的、指令驱动的格式（Terminal-style aesthetics）。
- **术语更迭**：
    - Distillation (提纯) / Contribution (反哺) 取代 Harvesting (收割)。
    - Foundry (母库) / Workshop (工作间) 取代 Mother-Base / Sub-Project。
- **探测逻辑**：优先探测 `.gemini/config.json` 中的 `skillPaths`，其次向上递归寻找 `.gemini/global_standard.md`。

## Risks / Trade-offs

- **[Risk] 指令集断层**：更名后旧项目的脚本可能失效。 → [Mitigation] 在 `global_standard.md` 中增加“术语映射”说明，并在短期内保持对旧指令的向前兼容。

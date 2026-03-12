# ADR-014: 开源化品牌重塑与路径动态化 (Open-Source Rebranding and Path Dynamization)

## Status
Accepted

## Context
随着 SOP 2.0 体系的成熟，项目计划向开源社区开放。然而，当前的文档中包含大量的硬编码物理路径（如 `D:\`）、组织特定名称（如 `Wuhan-Lab`）以及较强硬的术语（如“收割”）。这些因素阻碍了项目的普适性和社区友好度。我们需要一套完整的开源化方案，以提升品牌形象并解决跨环境兼容性问题。

## Decision
1. **确立新品牌**：正式将项目更名为 **`YOU-DRIVE-SOP`**。
2. **术语温和化**：将“资产收割（Harvesting）”统一更名为“资产沉淀与反哺（Asset Distillation & Contribution）”。
3. **路径抽象化**：引入 `{{FOUNDRY_ROOT}}` 占位符，并通过 `meta-path-discovery` 元技能实现基于向上递归的路径自动探测，彻底废弃绝对路径引用。
4. **文档门禁重塑**：建立开源标准的 `README.md` 和 `GETTING_STARTED.md`，并以“用户驱动（You Drive）”为中心重写核心宪法。

## Consequences
- **好处**：实现了项目的跨机器、跨平台无缝部署；确立了谦虚且专业的开源协作风格；增强了用户的掌控感。
- **约束**：所有的 Skill 开发者必须遵循 `meta-path-discovery` 的探测逻辑；旧有的脚本指令需适配新的术语表。

## Related Sub-Project
N/A (Project-Wide Rebranding)

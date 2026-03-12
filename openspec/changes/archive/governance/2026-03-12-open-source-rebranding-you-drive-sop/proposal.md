## Why

项目目前处于“私人实验室”状态，包含大量的硬编码物理路径（如 D:\...）、组织特定名称（如 Wuhan-Lab）以及较强硬的术语描述（如“收割”）。为了将其推向开源社区，我们需要确立 `YOU-DRIVE-SOP` 这一品牌调性，移除所有个人及地域敏感信息，并建立一套基于“路径自动探测”的技术基准，使任何用户都能在本地环境中快速部署并驱动这套 SOP。

## What Changes

- **确立品牌形象**：创建开源标准的 `README.md` 和 `GETTING_STARTED.md`。
- **全库脱敏与更名**：将“收割（Harvesting）”统一更名为“资产沉淀与反哺（Asset Distillation & Contribution）”。
- **路径动态化重构**：定义基于向上探测的路径发现逻辑，废弃绝对地址引用。
- **重写全局标准**：以 `YOU-DRIVE-SOP` 为主体重写 `global_standard.md`。

## Capabilities

### New Capabilities
- `path-discovery`: 用于自动定位母库（Foundry）根目录的元能力。

### Modified Capabilities
- 全量核心技能 (Meta Skills)：执行脱敏与更名 Patch。

## Impact
- 实现了项目的“即插即用”开源特性。
- 确立了专业的开源协作调性。

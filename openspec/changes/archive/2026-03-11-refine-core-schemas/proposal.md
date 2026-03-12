## Why

当前 SOP 2.0 体系缺乏统一的、工业级的规约模板（Schemas），导致子库在接入母库时环境对齐成本高，资产提纯过程容易受到业务变量污染，且架构决策缺乏结构化记录。本任务旨在建立一套标准的协议模板，以确保母库在扫描、提取和演进过程中的确定性。

## What Changes

- **建立环境协议 (env_schema)**：定义 Node 20 强制标准、禁止读取清单及关键依赖指纹。
- **建立提纯协议 (logic_schema)**：定义逻辑提取契约，强制执行“逻辑-UI 分离”和参数化去业务化。
- **建立决策协议 (decision_schema)**：规范 ADR 格式，关联子库 ID。
- **更新全局规约**：将这些 Schema 整合进 `foundry-initializing` 工作流。

## Capabilities

### New Capabilities
- `foundry-protocols`: 定义母库与子库交互的三大核心协议（Env, Logic, Decision）。

### Modified Capabilities
- N/A

## Impact
- 影响 `openspec/schemas/` 目录结构。
- 影响后续所有通过 `workshop-initializing` 接入的项目。
- 提高资产收割（Harvesting）的纯度和自动化程度。

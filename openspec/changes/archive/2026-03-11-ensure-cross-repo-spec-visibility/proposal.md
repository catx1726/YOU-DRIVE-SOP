## Why

虽然子库建立了技能链路，但目前存在两个隐患：
1. **链路不显式**：没有一个跨工具通用的路径存根（link.json）。
2. **规约盲区**：子库的 OpenSpec 工具无法自动感应到母库的 `foundry-protocols`，导致 AI 在子库中“目无王法”。

## What Changes

- **更新 `workshop-initializing`**：
    - 增加创建 `.gemini/link.json` 的物理动作。
    - 增加在子库 `openspec/` 目录下创建指向母库 `schemas/` 的引用，确保规约自动加载。

## Capabilities

### Modified Capabilities
- `foundry-protocols`: 强化子库初始化的标准，增加物理链路文件的要求。

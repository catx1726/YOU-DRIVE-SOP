## Why

目前子库在通过 `workshop-initializing` 对齐母库后，虽然建立了技能链路，但无法自动加载母库的 `global_standard.md` 行为宪法。这导致 AI 在子库会话中仍可能偏离母库定义的收割和开发规约。本任务旨在通过自动化生成子库 `GEMINI.md` 的方式，实现全局标准的强制性注入。

## What Changes

- **增强 `workshop-initializing` 技能**：在初始化流程末尾增加自动生成/更新子库根目录 `GEMINI.md` 的动作。
- **引用母库宪法**：在子库 `GEMINI.md` 中显式指向母库的全局标准文件路径。

## Capabilities

### New Capabilities
- N/A

### Modified Capabilities
- `foundry-protocols`: 更新子库对齐规约，明确标准注入（Standard Injection）的要求。

## Impact
- 影响所有新执行 `workshop-initializing` 的子项目。
- 确保子库的 AI 会话从第一分钟起就受到母库全局标准的约束。

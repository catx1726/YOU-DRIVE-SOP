## Why

在开源化初期，部分核心文档被转换为英文，这虽然提升了国际化调性，但对中文核心用户群体造成了阅读障碍。此外，目前 `README.md` 和 `GETTING_STARTED.md` 缺乏对 `OpenSpec` 和 `Superpowers` 这两大支柱工具的具体使用说明，导致新用户“知道目标，但不知道怎么握方向盘”。本任务旨在恢复中文表达，并注入详尽的工具链操作指南。

## What Changes

- **全量汉化**：将 `global_standard.md`、`meta-path-discovery/SKILL.md`、`README.md` 及 `GETTING_STARTED.md` 恢复为高质量中文。
- **注入工具指引**：
    - 在 `README` 中增加 `OpenSpec (opsx)` 的生命周期管理说明。
    - 在 `README` 中增加 `Superpowers` 的元能力与工程纪律说明。
- **增强入门指南**：在 `GETTING_STARTED` 中提供具体的指令示例（如 `/opsx:propose`, `activate_skill`）。

## Capabilities

### Modified Capabilities
- `foundry-protocols`: 增加关于“多语言支持与易用性”的文档建议。

## Impact
- 降低了 `YOU-DRIVE-SOP` 的上手门槛。
- 确立了母库文档的“中英双语”或“中文优先”协作基准。

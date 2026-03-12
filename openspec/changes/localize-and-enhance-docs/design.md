## Context

我们需要在保持 `YOU-DRIVE-SOP` 开源格调的同时，通过中文和详尽的说明书来“赋能”驾驶员。

## Goals

**1. 语言回归 (Localization)**
- 目标文件：`global_standard.md`, `path-discovery/SKILL.md`, `README.md`, `GETTING_STARTED.md`。
- 准则：准确、专业、去生硬感。

**2. 工具链透传 (Toolchain Education)**
- 内容：解释 `OpenSpec (Governance)` 与 `Superpowers (Execution)` 的分工与协作。

## Decisions

- **双语保留**：关键术语（如 Foundry, Workshop, Propose）保留英文，解释使用中文。
- **README 增强**：增加一个名为 `## 🛠️ 工具链手册` 的一级章节。
- **操作安全**：本任务实施全程使用 `meta-safe-executor` 记录。

## Risks / Trade-offs

- **[Risk] 文档臃肿** → [Mitigation] 使用渐进式披露，README 仅放核心指令，详细 API 链接至 `GETTING_STARTED`。

## Context

我们需要在子库中建立物理痕迹，以确保 OpenSpec 和 Gemini CLI 都能感知到母库的存在。

## Goals

**1. 建立 `link.json` 存根**
- 路径：子库 `.gemini/link.json`。
- 内容：记录 `motherBasePath`。

**2. 解决规约可见性**
- 方案：在子库执行 `openspec sync` 或手动将母库的 `openspec/schemas/*.md` 同步/引用至子库。
- 决策：在初始化时，强制将母库的 `schemas` 文件夹作为一个“挂载点”的概念注入。

## Decisions

- **link.json 结构**：
  ```json
  { "motherBasePath": "D:\\code\\2026\\Base-AI-Driven-Template" }
  ```
- **规约注入路径**：子库 `openspec/schemas/foundry/`。

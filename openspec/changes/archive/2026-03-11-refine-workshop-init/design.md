## Context

为了实现“母库宪法”在子库的自动落地，我们需要在 `workshop-initializing` 中增加一个物理文件的写入动作。Gemini CLI 会优先加载当前目录下的 `GEMINI.md`，因此这是注入全局指令的最优载体。

## Goals / Non-Goals

**Goals:**
- 在子库根目录自动生成 `GEMINI.md`。
- 注入对母库 `D:\code\2026\Base-AI-Driven-Template\.gemini\global_standard.md` 的强制引用。

**Non-Goals:**
- 本任务不涉及对母库 `global_standard.md` 内容本身的修改。

## Decisions

- **引用格式**：在 `GEMINI.md` 中使用 Markdown 链接并配合 `REQUIRED` 关键字。
- **文件策略**：若 `GEMINI.md` 已存在，执行增量追加（Append）而非覆盖（Overwrite），以保护子库原有的自定义配置。

## Risks / Trade-offs

- **[Risk] 路径变动**：若母库路径发生移动，子库的引用会失效。 → [Mitigation] 在 `workshop-initializing` 中保持路径变量的可维护性。

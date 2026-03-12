## Context

在 Windows 中，`Junction` (联接点) 是跨盘符引用的最佳方案。我们需要确保 AI 具备区分“本地真实文件”与“远程联接点”的能力，以防误删子库本地的私有资产。

## Goals

**1. 建立识别与清理逻辑**
- 动作：遍历 `.gemini/skills/` 目录。
- 判据：检查 `Attributes` 是否包含 `ReparsePoint` 标志。
- 例外：显式排除 `openspec-bridge` 等非链接文件夹。

**2. 重建引用链**
- 动作：扫描母库 `.gemini/skills/` 的一级子目录。
- 工具：`New-Item -ItemType Junction`。

## Decisions

- **幂等性保障**：每次“修复”前，先清理所有旧的联接点，防止因目标已存在导致创建失败。
- **路径参数化**：母库路径应从 `.gemini/link.json` 动态读取。

## Risks / Trade-offs

- **[Risk] 误删本地文件** → [Mitigation] 严格执行 `ReparsePoint` 属性检查，禁止对普通目录执行 `Remove-Item`。
- **[Risk] 路径深度限制** → [Mitigation] 保持扁平化目录结构。

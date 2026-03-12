## Context

为了将“智力资产”收割过程标准化，我们需要一个具备“缓冲区”概念的流水线。

## Goals

**1. 建立 `meta-distiller` 执行引擎**
- 第一阶段：在子库执行逻辑提取，生成参数化代码。
- 第二阶段：在 `.gemini/distill_stage/` 生成 Pattern 三件套和 Skill 初稿。
- 第三阶段：执行本地验证。

**2. 实现 Skill-Pattern 联动**
- Skill 文档中必须包含指向 Pattern 物理路径的硬链接。
- 确保子库挂载母库后，AI 能通过 Skill 找到 Pattern。

## Decisions

- **暂存区位置**：子库根目录 `.gemini/distill_stage/`。理由：方便用户通过文件树快速审核。
- **自动合并点**：集成在 `openspec-changes-archive` 的最后一步。
- **Skill 前缀**：强制使用 `common-` 前缀，并扁平化存放。

## Risks / Trade-offs

- **[Risk] 路径硬编码**：Skill 中的路径在不同机器下可能失效。 → [Mitigation] 使用相对于母库根目录的变量（如 `{{MOTHER_BASE}}`）或要求 AI 动态解析。
- **[Risk] 审核遗漏**：用户可能直接 Accept。 → [Mitigation] AI 在执行合并前，必须简要总结 Staging 中的变更产物。

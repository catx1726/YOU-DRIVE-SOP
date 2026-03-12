## Context

我们需要在全库范围内进行一次“存量清理”，将所有涉及资产生成的逻辑入口收窄。

## Goals

**1. 重定义 legacy-extractor 的终点**
- 旧逻辑：读取 -> 提炼 -> 写进 `openspec/specs/logic.md`。
- 新逻辑：读取 -> 识别 -> 触发 `meta-distiller` -> 写进 `.gemini/distill_stage/`。

**2. 统一术语与引用**
- 全局修正：将 `asset-harvesting` 字样更新为 `meta-distiller`。
- 引入 `mode: step-by-step`：由于对齐过程变复杂，相关技能应升级为分步模式。

## Decisions

- **legacy-extractor 保留项**：保留其“路径扫描”和“核心发现”的逻辑，这属于它的专业领域；移除其具体的“代码参数化”和“文件写入”逻辑，委托给 `meta-distiller`。
- **global_standard 修正**：作为最高宪法，必须首先修正。

## Risks / Trade-offs

- **[Risk] 用户习惯惯性**：用户可能习惯看 `logic.md`。 → [Mitigation] 在 `legacy-extractor` 中增加引导语：『提纯结果现已统一存入母库标准的 patterns 目录，请在 distill_stage 中查看。』

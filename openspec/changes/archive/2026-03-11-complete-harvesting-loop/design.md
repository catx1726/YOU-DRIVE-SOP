## Context

提纯（Distillation）是 SOP 2.0 的核心价值。我们需要将碎片化的任务产物转化为结构化的、可索引的知识。

## Goals / Non-Goals

**Goals:**
- 定义 `patterns/` 的物理标准：`index.ts` (逻辑), `index.test.ts` (Vitest), `README.md` (契约)。
- 定义 `skills/` 的提纯逻辑：基于 `writing-skills` 自动从代码逻辑生成指令集。
- 实现跨库写入：在子库操作时，自动通过 `link.json` 或全局路径定位母库。

**Non-Goals:**
- 不涉及自动化 UI 截图或视觉资产的提纯。

## Decisions

- **路径识别**：`asset-harvesting` 技能必须首先读取 `.gemini/link.json` 或母库环境变量，以确定资产反哺的目标位置。
- **参数化标准**：采用正则表达式扫描，强制将业务特有词汇（词库由 `env.md` 提供）替换为 `{{VAR}}`。
- **Skill 命名**：所有提纯后的技能统一使用 `common-` 前缀，并放置在母库 `skills/` 根目录（遵循扁平化原则）。

## Risks / Trade-offs

- **[Risk] 收割逻辑冗余**：多次收割导致母库混乱。 → [Mitigation] `asset-harvesting` 必须执行“母库查重”步骤。
- **[Risk] 测试环境差异**：子库测试环境与 Node 20 不一致。 → [Mitigation] 强制在母库 Patterns 下进行二次本地验证。

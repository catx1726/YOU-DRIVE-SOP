## Context

我们要执行的是一次“智力对齐”。我们需要识别出上游工具中被我们“自行发明”替代的原生更好方案。

## Goals

**1. 深度扫描策略 (Scanning Strategy)**
- **OpenSpec**: 重点看 `openspec.yaml` 的高级配置、状态机定义及 specs 间的 `unlocks` 逻辑。
- **gemini-superpowers**: 重点看其 Skill 目录下的 `SKILL.md`，特别是针对“对抗幻觉”的压力测试场景。
- **superpowers**: 重点看其底层的“能力模型”和跨 AI 平台的兼容性逻辑。

**2. 品牌致敬 (Attribution)**
- 在 README 增加 `Credits & Dependencies` 章节。

## Decisions

- **执行模式**：采用 `legacy-extractor` + `meta-distiller` 的组合拳。
- **分步逻辑**：每处理完一个 `tools/` 下的子库，必须输出一份《功能挖掘简报》，待用户确认哪些点值得并入母库后再执行写入。

## Risks / Trade-offs

- **[Risk] 功能冲突**：上游逻辑可能与我们现有的 meta 技能冲突。 → [Mitigation] 优先采用“增强（Enhance）”而非“替换（Replace）”策略，除非上游方案具有绝对优势。

# ADR-018: 子库看板式 GEMINI.md 与交互式引导 (Dashboard and Interactive Onboarding)

## Status
Accepted

## Context
用户反馈在 `workshop-initializing` 完成后，往往不知道接下来该执行什么指令。目前的 `GEMINI.md` 仅作为行为宪法的引用载体，缺乏直观的“仪表盘”功能。我们需要一种机制，在初始化成功后立即为用户呈现“第一步操作”，并提供常驻的指令看板以降低记忆门槛。

## Decision
1. **重塑 GEMINI.md 为操作看板**：更新 `workshop-initializing` 技能，使其生成的 `GEMINI.md` 顶部包含「🚀 快速操作看板」。看板需分类列出 Legacy 逆向与 Feature 开发的核心指令流。
2. **引入交互式 Handover 环节**：在初始化流程的末尾，强制 AI 停顿并向用户提问其当前的开发意图（A/B 路径选择），并根据选择提供针对性的第一步指令指引。
3. **动态路径注入**：看板内容需支持 `{{FOUNDRY_ROOT}}` 的动态替换，确保在任何环境下链接均有效。

## Consequences
- **好处**：极大地提升了新用户的“第一秒体验”；消除了初始化后的认知真空期；增强了框架的教育引导能力。
- **约束**：初始化动作增加了交互成本（需用户输入 A/B）；需要保持 `GEMINI.md` 模板的简洁，避免信息过载。

## Related Sub-Project
N/A (SOP 2.0 User Experience Refinement)

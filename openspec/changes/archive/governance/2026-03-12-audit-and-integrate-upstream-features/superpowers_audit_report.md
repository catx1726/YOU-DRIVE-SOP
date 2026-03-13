# Superpowers 源库审计简报 (Origin Upstream Audit)

## 1. 架构模型：指令优先权
- **Priority Stack**：User > Skill > System。
- **[集成建议]**：在 `YOU-DRIVE-SOP` 核心宪法中引入“主权栈”概念，明确 `GEMINI.md` 为用户行使最高驾驶权的入口。

## 2. 跨平台兼容性：工具抽象
- **Tool Mapping**：支持不同 IDE/CLI 的工具名称适配。
- **[集成建议]**：在 `meta-safe-executor` 中建立“动作抽象层”，使 Skill 文档不再绑定特定的 API 名称。

## 3. 自动化闭环：物理钩子
- **Junction Hooks**：利用 `.git/hooks` 或扩展原生钩子执行验证。
- **[集成建议]**：在 `workshop-initializing` 中增加“安全钩子注入”，实现真正的“无感审计”。

## 4. 品牌合规
- **Credits**：必须致敬 `Jesse (obra)` 及 `Barret Storck` 的杰出贡献。

## ADDED Requirements

### Requirement: 上游智力对齐 (Upstream Alignment)
母库 SHALL 定期同步并对齐其核心依赖工具（OpenSpec & Superpowers）的原生能力。
- **深度挖掘**：必须通读上游文档中的高级指令（如 specs 依赖、验证钩子）。
- **原生优先**：若上游提供了原生支持的功能（如 spec sync），应优先对齐其逻辑而非自行发明。
- **合规声明**：所有开源发布版本必须显式标注对 OpenSpec 和 Superpowers 的依赖与致敬。

#### Scenario: 挖掘 OpenSpec 隐藏能力
- **WHEN** 执行 `audit-upstream-features`。
- **THEN** AI 识别出 OpenSpec 中关于 `unlocks` 自动依赖推导的高级用法，并建议将其更新至 `foundry-protocols`。

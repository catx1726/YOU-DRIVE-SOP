## ADDED Requirements

### Requirement: 链接自愈 (Link Self-Healing)
系统 SHALL 能够自动识别并修复子库中失效的技能映射。
- **属性识别**：必须能够通过 `ReparsePoint` 属性识别物理联接点（Junction）。
- **幂等清理**：在重建链接前，SHALL 安全移除现有的联接点，同时严格保护非链接的本地文件夹（如 `openspec-bridge`）。
- **物理重建**：使用 `Junction` 类型重建从子库到母库技能的一对一映射。

#### Scenario: 一键修复损坏的链接
- **WHEN** 用户发出“修复链接”或“刷新技能”指令。
- **THEN** AI 识别当前工作区所有属性为 `ReparsePoint` 的子文件夹，执行安全清理，并根据 `link.json` 定义的母库路径重建所有技能的 Junction 映射。

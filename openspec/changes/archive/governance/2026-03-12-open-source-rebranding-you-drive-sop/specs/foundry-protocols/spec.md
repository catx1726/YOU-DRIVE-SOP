## ADDED Requirements

### Requirement: 品牌与脱敏 (Rebranding & Sanitization)
所有文档与代码 SHALL 遵循 `YOU-DRIVE-SOP` 品牌标准并执行脱敏。
- **禁止硬编码**：禁止出现任何特定于开发者的物理绝对路径（如 `D:\`）。
- **去组织化**：移除 “Wuhan-Lab”、“华胜”等特定标识，统一替换为 “Foundry”、“Workshop” 或 “Core Library”。
- **术语一致性**：资产处理动作必须使用 “Distillation”（提纯）与 “Contribution”（反哺）。

#### Scenario: 开源化文档生成
- **WHEN** AI 生成 README。
- **THEN** 系统自动使用 `YOU-DRIVE-SOP` 品牌头，并以“驾驶者（You）”为中心进行叙述。

### Requirement: 路径自动探测 (Path Discovery)
系统 SHALL 具备自动定位资源根目录的能力。
- **动态占位符**：所有的 Skill 引用必须使用 `{{FOUNDRY_ROOT}}` 占位符。
- **探测逻辑**：AI 必须首先执行根目录探测逻辑，获取物理路径并实时填充占位符。

#### Scenario: 跨环境执行
- **WHEN** 在一个新的 Linux 环境下部署本库。
- **THEN** AI 通过向上递归找到 `.gemini/global_standard.md`，自动识别出当前的母库根目录，无需用户修改 Skill 源码。

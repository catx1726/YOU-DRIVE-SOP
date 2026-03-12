## MODIFIED Requirements

### Requirement: 环境指纹识别 (workshop-initializing)
子库对齐 SHALL 不仅限于指纹识别，还必须包含母库标准的自动化注入。
- 在初始化末尾，必须在子库根目录创建或更新 `GEMINI.md`。
- `GEMINI.md` 必须包含对母库全局标准（Global Standard）的强制引用声明。

#### Scenario: 自动化宪法注入
- **WHEN** 子库执行 `workshop-initializing` 成功挂载母库技能后。
- **THEN** 系统自动在子库生成 `GEMINI.md`，并在其中写入：『本项目的 AI 行为流必须遵循母库全局标准 (D:\code\2026\Base-AI-Driven-Template\.gemini\global_standard.md)』。

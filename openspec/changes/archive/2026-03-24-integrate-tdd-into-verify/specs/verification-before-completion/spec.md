## MODIFIED Requirements

### Requirement: Pre-flight Verification (The Gate Function)
AI 引擎在任何归档或提交 claim 前，**SHALL** 首先读取项目目录下的 `openspec/config.yaml` 或 `package.json` 获取项目级测试命令 `{{TEST_COMMAND}}`，并**强制执行**该命令。

#### Scenario: 自动化测试不通过
- **WHEN** 任何自动化测试失败 (exit code != 0)
- **THEN** AI 必须立即停止验证流程，严禁进入手动 Scenario 比对环节，并向用户报告测试失败现场。

#### Scenario: 自动化测试通过
- **WHEN** 所有测试均通过
- **THEN** AI 方可进入手动 Scenario 比对环节。

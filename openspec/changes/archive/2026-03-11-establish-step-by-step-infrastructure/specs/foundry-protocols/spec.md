## ADDED Requirements

### Requirement: 分步执行协议 (Step-by-Step Execution)
对于所有被标记为 `mode: step-by-step` 的技能，系统 SHALL 强制执行分步控制流。
- **任务规划**：在开始前，必须生成一份临时任务列表。
- **状态持久化**：必须在 `.gemini/skill_progress.md` 中实时记录完成状态。
- **原子操作**：每回合仅执行一个原子任务块，并在完成后主动暂停等待确认。
- **环境闭环**：任务全部完成后，必须物理删除 `.gemini/skill_progress.md`。

#### Scenario: 复杂初始化的安全步进
- **WHEN** 激活 `workshop-initializing`（已标记为 `step-by-step`）。
- **THEN** AI 停止一次性输出，先展示任务列表，每完成一步（如：建立链路）就更新 `skill_progress.md` 并询问用户是否继续。

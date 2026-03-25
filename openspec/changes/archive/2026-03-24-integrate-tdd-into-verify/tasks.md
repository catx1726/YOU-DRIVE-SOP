## 1. 规约与环境自检 (Mandatory Setup)
- [x] 1.1 确认当前分支为 `issue-integrate-tdd`
- [x] 1.2 确认 `.gemini/ops_changelog.md` 审计表格已准备好

## 2. 核心实施 (Core Implementation)
- [x] 2.1 修改 `.gemini/skills/verification-before-completion/SKILL.md`，植入 Pre-flight 测试环节
- [x] 2.2 验证：确保 SKILL 已包含对 `{{TEST_COMMAND}}` 的探测逻辑

## 3. 过程合规性校验 (Compliance Verification)
- [x] 3.1 确认所有写操作均记录在 `ops_changelog.md` 中
- [x] 3.2 运行 `/opsx:verify` 并验证门控熔断功能

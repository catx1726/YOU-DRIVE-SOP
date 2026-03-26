## Context
目前的 `verification-before-completion` 依赖 AI 的自觉性，且测试命令硬编码。在多语言场景下不具备普适性。

## Decisions
1. **配置驱动设计**: 在 `openspec/config.yaml` 增加 `runtime.test_command` 锚点。
2. **物理熔断机制**: 修改 Skill 源码，若测试 Exit Code 非 0，则中断所有 claim 动作。

## Risks / Trade-offs
- [Risk] 环境缺失相应测试引擎 -> [Mitigation] Skill 提示用户检查 runtime 配置。

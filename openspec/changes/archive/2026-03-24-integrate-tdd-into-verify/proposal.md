## Why

当前 `/opsx:verify` 验证逻辑与项目内的自动化测试（如 `npm test`）存在割裂。AI 可能在未执行自动化测试的情况下，仅凭简单的 Scenario 比对即通过验证，这违反了 SOP 2.0 “证据先行”的原则。

## What Changes

- **增强验证逻辑**: 在 `verification-before-completion` 技能中，强制引入 `Pre-flight Test Phase`。
- **配置化测试**: 使用 `openspec/config.yaml` 定义项目级 `test_command`，而非硬编码。
- **强制熔断**: 若 `Pre-flight Test` 失败，则直接拦截归档/提交操作。

## Capabilities

### Modified Capabilities
- `verification-before-completion`: 将测试命令探测与执行作为强制性前置检查。

## Impact

- **流程合规性**: 确保所有提纯与归档逻辑均在自动化测试通过的基础上进行。
- **质量门控**: 提升了 AI 提交的物理代码质量。

## Why
当前 `/opsx:verify` 验证逻辑与项目内的自动化测试（如 `npm test`）存在割裂。为了对齐 SOP 2.0 “证据先行”原则，必须将自动化测试作为验证的前置硬熔断。

## What Changes
- **增强验证逻辑**: 在 `verification-before-completion` 技能中，强制引入 `Pre-flight Test Phase`。
- **配置化测试**: 使用 `openspec/config.yaml` 定义项目级 `test_command`。
- **强制熔断**: 若 `Pre-flight Test` 失败，则直接拦截归档/提交操作。

## Capabilities
### Modified Capabilities
- `verification-before-completion`: 将测试命令探测与执行作为强制性前置检查。

## Impact
- 提升了 AI 提交的物理代码质量，确保所有归档逻辑均在测试通过的基础上进行。

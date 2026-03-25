## Context
目前 `verification-before-completion` 技能依赖手动执行测试，且测试命令硬编码为 `npm test`。在 SOP 2.0 框架下，这导致了“开发环境配置与验证协议”的耦合。

## Goals / Non-Goals
**Goals:**
- 将测试执行入口抽象为配置变量 `{{TEST_COMMAND}}`。
- 实现验证阶段的物理熔断：测试失败则直接中断流程。

**Non-Goals:**
- 不重构现有项目的测试框架（由具体 Workshop 决定）。

## Decisions
1. **配置驱动设计**: 在 `openspec/config.yaml` 中增加 `runtime.test_command` 节点，允许子库根据自身技术栈（Vitest, Pytest, Cargo 等）定义入口。
2. **强制门控设计**: 修改 `verification-before-completion` 技能的 `The Gate Function`，将测试执行提升为“前置守卫”。

## Risks / Trade-offs
- [Risk] 配置丢失或未定义 → [Mitigation] 系统自动回退至默认 `npm test` 并警告。

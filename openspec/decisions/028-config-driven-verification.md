# ADR 028: 配置驱动的自动化校验 (Config-Driven Verification)

- **状态**: Accepted
- **日期**: 2026-03-24
- **主题**: 将测试命令从硬编码迁移至配置管理

## 核心决策
1. **统一配置**: 在 `openspec/config.yaml` 中引入 `runtime.test_command`，作为所有 Workshop 项目的“测试校验”唯一配置入口。
2. **强制前置门控**: 更新 `verification-before-completion` 技能，AI 在执行任何 `Verify` 前，必须显式读取该配置并执行对应的自动化测试。

## 影响评估
- 解耦了特定语言测试入口（如从 `npm test` 到 `pytest` 或 `go test` 的迁移）。
- 确保了 SOP 2.0 的“质量守卫”机制对于所有项目类型均有效。

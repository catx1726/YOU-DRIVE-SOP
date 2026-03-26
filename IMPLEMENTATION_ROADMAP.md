# 13 步协议自动化路线图 (Implementation Roadmap)

本文档追踪 13 步生产协议中“流程节点”的物理自动化程度，作为 SOP 2.0 的任务追踪真值源。

| 节点 | 描述 | 状态 | Gap 分析 | 优先级 |
| :--- | :--- | :--- | :--- | :--- |
| **04** | `/opsx:propose` 联动 `writing-plans` | 已落地 | - | - |
| **05** | `/opsx:apply` 联动 `executing-plans` | 已落地 | - | - |
| **06** | TDD 强制化 | 弱实现 | 目前依赖 AI 自觉，需强化 enforcement | 高 |
| **07** | `meta-safe-executor` CI 校验 | 部分实现 | CI 尚未校验 ops_changelog.md | 中 |
| **08** | 产出物证据 (TDD) | 已落地 | - | - |
| **09** | `/opsx:verify` 前置测试 | 已落地 | - | - |
| **10** | `meta-distiller` 提纯 | 半自动 | 需与 `archive` 绑定 | 中 |
| **13** | PR 合规性校验 | 半自动 | CI 校验 arch 目录 | 低 |
| **14** | 测试命令配置化 (Test Config) | 待实现 | 需要在每个子库按栈适配 test_command | 高 |

---
*注：每一个节点的优先级均由“自动化覆盖度”与“流程合规性”共同决定。*

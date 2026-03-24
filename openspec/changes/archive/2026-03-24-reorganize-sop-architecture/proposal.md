## Why

当前 YOU-DRIVE-SOP 2.0 的架构定义分散在 `GEMINI.md`, `SOP_CORE_MANUAL.md` 和 `ARCHITECTURE.md` 中，导致 AI 引擎在理解“治理 (OpenSpec)”与“执行 (Superpowers)”的协作关系时存在认知负担。通过本次重构，我们将确立“唯一真值源 (SSOT)”，显性化“骨架与肌肉”模型，并硬化母库的自演进 (Self-Evolution) 能力，从而降低系统的认知熵，提升资产提纯的确定性。

## What Changes

- **文档收口 (Consolidation)**: 将所有物理架构、角色定义与核心协议从碎片化文档中提取，统一收口至 `ARCHITECTURE.md`。
- **入口硬化 (Onboarding)**: 合并 `AGENTS.md` 与 `GEMINI.md`，建立唯一且具备自动自检能力的 AI 登舰入口。
- **显性化模型 (Explicit Model)**: 增加“治理-执行”二元模型定义，明确 OpenSpec (骨架) 负责状态与流程，Superpowers (肌肉) 负责原子执行质量。
- **架构图补完 (Micro-Flows)**: 在 `ARCHITECTURE.md` 中补充 `meta-distiller` 提纯路径、`OpenSpec` 状态机等微观流程图。
- **递归模式 (Recursive Mode)**: 在 `GETTING_STARTED.md` 中正式定义母库自进化配置，支持母库作为子库使用的闭环。
- **引擎层标注 (Engine Labeling)**: 更新架构图，显式标注 Superpowers 执行层及其与 `meta-safe-executor` 的逻辑关联。

## Capabilities

### New Capabilities
- `skeleton-muscle-governance`: 定义治理协议与执行技能的二元协作标准。
- `foundry-self-evolution`: 提供母库作为子库进行自递归演进的配置规约与操作指南。
- `micro-flow-visualization`: 提供核心资产生命周期（提纯、提案、归档）的微观流程可视化定义。

### Modified Capabilities
- `foundry-architecture-blueprint`: 更新架构蓝图，整合 Superpowers 执行层与分布式文档结构。
- `foundry-bootstrapping`: 修改 AI 登舰自检清单，整合 AGENTS 角色定义。
- `vcs-lifecycle-automation`: 强化 OpenSpec 状态机在自演进模式下的 VCS 自动化行为。

## Impact

- **文档结构**: `ARCHITECTURE.md`, `GEMINI.md`, `SOP_CORE_MANUAL.md`, `GETTING_STARTED.md` 将发生重大内容重组。
- **认知负荷**: 大幅降低新 AI 引擎登舰时的初始化成本。
- **资产流转**: 提升 `meta-distiller` 在母库自演进场景下的工作确定性。
- **依赖关系**: 建立 `OpenSpec` 提案与 `Superpowers` 技能之间的显式依赖。

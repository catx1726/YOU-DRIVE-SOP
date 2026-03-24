## Context

目前项目处于 SOP 2.0 演进的中期，虽然核心组件（OpenSpec, Superpowers, Distiller）已到位，但文档体系呈现“生长式”碎片化。`GEMINI.md` 作为入口包含过多具体角色定义，而 `SOP_CORE_MANUAL.md` 与 `ARCHITECTURE.md` 在“如何工作”与“架构是什么”之间存在定义重叠。此外，母库自演进（Foundry as Workshop）的逻辑仅存在于开发者意识中，缺乏物理配置指引。

## Goals / Non-Goals

**Goals:**
- **单一真值化**: 确立 `ARCHITECTURE.md` 为架构与协议的唯一权威源。
- **入口极简化**: 简化 `GEMINI.md`，使其仅负责登舰自检与路由。
- **逻辑显性化**: 建立“骨架 (OpenSpec) - 肌肉 (Superpowers)”的二元协作模型说明。
- **递归闭环**: 实现母库自演进模式的文档化与配置标准化。

**Non-Goals:**
- **重写代码**: 本次变更不涉及 `openspec` 引擎或 `meta-distiller` 的核心逻辑修改。
- **更换工具**: 不引入新的第三方治理工具。

## Decisions

### 1. 文档职责重组 (SSOT)
- **Decision**: 将 `SOP_CORE_MANUAL.md` 中的物理架构描述与 `GEMINI.md` 中的角色详细定义全部迁移至 `ARCHITECTURE.md`。
- **Rationale**: 减少 AI context 中的重复信息，防止不同文档对同一架构的细微描述差异导致推理幻觉。
- **Alternative**: 保持现状，通过链接互相引用。但 AI 往往会全量读取文件，冗余依然存在。

### 2. 入口合并与自动化引导
- **Decision**: 删除 `AGENTS.md`，将其核心角色逻辑（Manager, Developer, AI Engine）合并进 `GEMINI.md` 的 [CRITICAL-BOOT-SEQUENCE] 章节。
- **Rationale**: 开发者（特别是 AI）进入仓库的第一眼应该只有一个指引。
- **Alternative**: 保留 `AGENTS.md` 作为详细手册，但这增加了跳转深度。

### 3. 显性化“骨架-肌肉”协作模型
- **Decision**: 在 `ARCHITECTURE.md` 中引入 `Engine` 层的分层定义：OpenSpec 为 **State Layer** (Skeleton)，Superpowers 为 **Action Layer** (Muscle)。
- **Rationale**: 明确“什么时候做”与“怎么做”的边界。

### 4. 递归模式标准化
- **Decision**: 在 `GETTING_STARTED.md` 中增加配置示例，展示如何将本地母库路径作为 `FOUNDRY_PATH` 进行自演进。
- **Rationale**: 消除母库开发者修改 `skills/` 时的流程违和感。

## Risks / Trade-offs

- **[Risk]** 链接断裂 → **Mitigation**: 在重组后手动或通过脚本检查所有 `.md` 文件间的相对路径引用。
- **[Risk]** 信息丢失 → **Mitigation**: 采用“先合并后删除”的策略，并在 `proposal.md` 中详细对照修改点。
- **[Risk]** AI 惯性认知 → **Mitigation**: 在 `global_standard.md` 中强化对新 SSOT 路径的感知指令。

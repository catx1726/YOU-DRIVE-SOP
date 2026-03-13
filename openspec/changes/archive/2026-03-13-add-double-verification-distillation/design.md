## Context

母库纯净度是 YOU-DRIVE-SOP 框架作为智力中枢的核心底线。

## Goals

**1. 建立“本地预验 (Local Pre-verify)”逻辑**
- 环节：`meta-distiller` 的 Staging 阶段。
- 动作：AI 强制在子库目录执行 `npm run vitest`。
- 门禁：测试未通过前，禁止输出“准备合并”指令。

**2. 建立“母库复验 (Foundry Re-verify)”逻辑**
- 环节：`/opsx:archive` 触发的合并阶段。
- 动作：AI 将 Staging 资产物理拷贝至母库后，**立即切换上下文至母库根目录**并运行测试。
- 原子撤回：若测试失败，立即执行 `rm -rf`（母库端）并将资产保持在子库端。

## Decisions

- **复验基准**：以母库的 Node 20 环境为准。理由：确保资产具备跨项目兼容性。
- **回滚粒度**：文件级原子操作。
- **用户透明度**：复验过程必须实时打印测试日志，让用户看见“考试”过程。

## Risks / Trade-offs

- **[Risk] 环境差异导致假阴性** → [Mitigation] 要求 Pattern 的 `index.test.ts` 必须完全 Mock 所有外部副作用。
- **[Risk] 性能开销** → [Mitigation] 仅针对 Staging 资产执行定向测试扫描，不运行全量母库测试。

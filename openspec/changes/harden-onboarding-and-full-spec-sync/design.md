## Context

当前 SOP 2.0 在初始化阶段的“信息传递”是不完整的。
- **子库 (Workshop)** 初始化时，仅选择了 `schemas` 等少量目录进行同步，忽略了 `specs/` 目录。
- **母库 (Foundry)** 初始化时，如果缺失了关键的生产协议（如 `vcs-lifecycle-automation`），子库初始化后也将缺失这些核心能力。
- **引导环节**：初始化完成后，AI 未能向用户展示其获得的“能力清单”，用户对系统是否就绪感到不透明。

## Goals / Non-Goals

**Goals:**
- **物理同步闭环**：实现母库 `openspec/` 的全量同步，包括 `specs`, `schemas`, `protocols`。
- **模板种子化**：在母库中预置核心规约种子，缺失时自动补全。
- **透明引导**：在子库初始化末尾，输出物理文件审计报告。

**Non-Goals:**
- **自动修复 Git 冲突**：同步过程中的冲突处理。
- **跨机器网络同步**：目前仅限于本地路径或文件系统的同步。

## Decisions

- **递归同步策略**：使用物理文件拷贝（或 Junction）同步母库的 `openspec/` 目录。
- **模板补全**：在 `foundry-initializing` 中硬编码核心规约的“最小可行性模板”，作为种子。
- **GEMINI.md 注入动态检测**：在子库的 `GEMINI.md` 中增加基于 `link.json` 的动态状态显示逻辑。

## Risks / Trade-offs

- **[Risk]** 同步可能覆盖子库已有的本地配置 -> **[Mitigation]** 仅对 `specs/` 等只读规约目录执行全量同步，对 `config.yaml` 执行 Deep Merge。
- **[Risk]** 母库路径变更导致链路失效 -> **[Mitigation]** 在 `workshop-initializing` 中强化 `link.json` 的“自愈提示”。

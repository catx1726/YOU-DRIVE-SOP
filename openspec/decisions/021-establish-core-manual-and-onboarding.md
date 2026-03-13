# ADR 021: 建立核心治理手册与 AI 登舰看板

## 状态 (Status)
已通过 (Accepted)

## 上下文 (Context)
随着 SOP 2.0 体系的完善，项目逻辑从简单的“代码实现”转向了“规约驱动”。新进入项目的 AI 代理和人类开发者往往难以快速理解 `.gemini` 和 `openspec` 之间的物理联动逻辑，导致执行过程中出现“意图漂移”或“流程坏账”。

## 决策 (Decision)
1.  **物理手册固化**：创建 `SOP_CORE_MANUAL.md`，通过“逻辑刚性”、“资产循环”和“人机协议”三个核心章节，将 SOP 2.0 的黑盒逻辑透明化。
2.  **AI 登舰看板 (Onboarding Dashboard)**：创建 `GEMINI.md` 作为 AI 代理的入口。该看板强制要求 AI 在启动任务前进行“物理握手”与“自检”，确保其对齐规约。
3.  **四层治理结构**：正式确立 `Constitution -> Config -> Protocols -> Skills` 的四层物理隔离体系。

## 后果 (Consequences)
- **正面**：显著降低了 AI 产生幻觉的概率；新 AI 的上手成本降低；流程具备了物理可追溯性。
- **负面**：文档维护成本略有增加，需在每次重大架构变更时同步更新手册。

---
*Created on 2026-03-13 by YOU-DRIVE-SOP Engine.*

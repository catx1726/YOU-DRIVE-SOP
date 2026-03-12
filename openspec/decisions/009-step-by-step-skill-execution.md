# ADR-009: 复杂技能的分步步进执行机制 (Step-by-Step Execution for Complex Skills)

## Status
Accepted

## Context
随着 SOP 2.0 体系的演进，元技能（如初始化、资产收割）的逻辑变得越来越复杂，往往包含多个物理文件操作和跨库指令。在长对话或 Token 受限的情况下，AI 一次性输出全量指令极易导致执行截断、步骤丢失或上下文漂移。我们需要一种增强的执行机制，确保复杂任务的原子化与确定性。

## Decision
1. **引入 mode: step-by-step 元数据**：在 `SKILL.md` 中增加显式标志，指示该技能必须分步执行。
2. **建立 meta-step-runner 元技能**：定义通用的分步控制逻辑，包括生成临时进度文件和每步确认。
3. **物理进度持久化**：使用 `.gemini/skill_progress.md` 记录当前执行状态，使 AI 具备物理上的“短时记忆”，支持断点续传。
4. **改造核心初始化技能**：将 `foundry-initializing` 和 `workshop-initializing` 升级为分步模式，并按 `[ ]` 任务列表重构其 Workflow。

## Consequences
- **好处**：极大地提高了复杂任务的成功率和可观测性；实现了执行过程的“原子化”确认；即便对话中断，也能通过读取物理文件找回进度。
- **约束**：执行过程需要用户更多的交互（输入 `next`）；要求技能编写者严格按照分步任务列表进行结构化描述。

## Related Sub-Project
N/A (SOP 2.0 Reliability Refinement)

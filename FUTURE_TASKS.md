# 未来研究与战略议题 (Future Research & Strategic Initiatives)

本文档用于记录 YOU-DRIVE-SOP 2.0 体系中，那些具有高战略价值但需要深度探索才能确定实施方案的议题。

---

## 1. Policy Engine 物理熔断机制 (Tech Spike)

- **目标**: 实现物理层的“强拦截”，而非 Skill 层的“软约束”。
- **研究方向**:
  - [ ] **Gemini CLI Hooks**: 调研 `BeforeTool` 或 `BeforeWrite` 原生钩子的可行性。
  - [ ] **TypeScript 插件**: 研究是否需要开发一个本地插件来读取 `.gemini/policies/safety.toml` 并实现熔断逻辑。
  - [ ] **跨平台兼容性**: 确保 Policy Engine 在 Windows, macOS 和 Linux 下行为一致。
- **验收标准**: 在未获得用户显式确认前，AI **物理上无法**调用 `run_shell_command("rm -rf ...")`。

## 2. 双环状态模型深度融合 (Architecture Design)

- **目标**: 打通 OpenSpec (战略外环) 与 Superpowers (战术内环) 的状态同步，实现无缝嵌套。
- **研究方向**:
  - [ ] **状态上报机制**: 设计一个可靠的机制，让 `write_todos` 的完成状态能自动更新 OpenSpec `tasks.md` 中的 `- [x]`。
  - [ ] **任务嵌套模型 (Nested Changes)**: 定义当一个 `tasks.md` 条目过于复杂时，是应该“深化”为更多 todo，还是“升级”为一个独立的子 Change。
  - [ ] **`tracker_create_task` 的定位**: 明确 `tracker_create_task` 在双环模型中的角色。它是 `write_todos` 的替代品，还是用于更细粒度的“微操环”？
- **验收标准**: 产出一份名为 **"Dual-Loop State Model"** 的 ADR (Architecture Decision Record)，并更新 `ARCHITECTURE.md` 中的相关流程图。

## 3. OpenSpec vs. Superpowers 深度对比 (Philosophical & Mechanical Analysis)

- **目标**: 彻底澄清 OpenSpec 与 Superpowers 的哲学、边界、机制与集成模式，形成 SOP 2.0 的“第一性原理”文档。
- **研究方向**:
  - [ ] **哲学与愿景 (Philosophy & Vision)**: 每个工具集最初被设计用来解决的核心问题是什么？（例如：OpenSpec 解决“变更治理”，Superpowers 解决“AI 行为约束”）。
  - [ ] **范围与边界 (Scope & Boundary)**: 一个工具的责任终点和另一个工具的责任起点在哪里？绘制一张清晰的“责任边界图”。
  - [ ] **机制与实现 (Mechanism & Implementation)**: OpenSpec 通过 CLI 和文件系统进行交互；Superpowers 主要通过 Prompt 注入和工具调用。这种机制差异如何影响它们在 SOP 2.0 中的角色？
  - [ ] **集成模式 (Integration Pattern)**: 最终确定并文档化“骨架-肌肉”模型的具体集成细节，包括数据流、状态同步和错误处理。
- **验收标准**:
  1. 产出一份名为 **"ADR: OpenSpec & Superpowers Integration Model"** 的决策记录。
  2. 在 `ARCHITECTURE.md` 中最终固化“二元模型”的图示与文字定义，使其无需进一步解释即可被新的 AI 或开发者理解。

---
*当以上任一议题的研究成熟后，应通过 `/opsx:propose "议题名称"` 将其转化为可执行的 OpenSpec Change。*

# ADR 022: 加固 AI 登舰链条与物理握手协议

## 状态 (Status)
已通过 (Accepted)

## 上下文 (Context)
在初次部署或新 AI 接入时，由于缺乏强制性的上下文引导，AI 引擎往往无法自动识别 `SOP_CORE_MANUAL.md` 等治理文档，导致“智力链条”断裂，用户必须手动下达复杂的引导指令。

## 决策 (Decision)
1.  **初始化注入**：修改 `foundry-initializing` 技能，在 Step 4 强制 AI 执行物理手册探测与自检汇报。
2.  **快速启动挂钩**：在 `GETTING_STARTED.md` 顶部增加“第 0 步：AI 登舰自检”，引导用户主动触发 AI 规约对齐。
3.  **开机脚本化**：在 `GEMINI.md` 注入强制性的 `Boot Sequence`。利用 Gemini CLI 自动加载该文件的特性，实现 AI 进入工作区后的“开机即握手”。

## 后果 (Consequences)
- **正面**：实现了 AI 协作的“即插即用”，确保了规约在不同 AI 引擎间的连续性。
- **负面**：对 `GEMINI.md` 的格式有严格要求，需防止因格式错误导致 CLI 加载失败。

---
*Created on 2026-03-13 by YOU-DRIVE-SOP Engine.*

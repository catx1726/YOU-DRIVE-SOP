# ADR-004: 子库全局标准的自动化注入 (Automated Global Standard Injection)

## Status
Accepted

## Context
在建立 Foundry-Workshop 链路后，子库虽然可以访问母库技能，但无法自动加载母库的行为宪法（`global_standard.md`）。这导致 AI 在子库会话中可能忽略资产收割门禁或环境对齐要求。我们需要一种机制，确保子库的 AI 环境从初始化起就受到母库标准的强制约束。

## Decision
1. **自动化生成 GEMINI.md**：更新 `workshop-initializing` 技能，使其在对齐流程末尾自动在子库根目录创建或更新 `GEMINI.md` 文件。
2. **强制引用声明**：在生成的 `GEMINI.md` 中注入对母库绝对路径下 `global_standard.md` 的引用。
3. **增量更新策略**：若子库已存在 `GEMINI.md`，系统应采用增量追加（Append）模式，避免覆盖用户原有的自定义指令。

## Consequences
- **好处**：实现了“母库立宪，子库守法”的自动化闭环；减少了手动配置成本；确保了跨项目的 AI 开发行为高度一致。
- **约束**：子库的初始化必须成功完成链路挂载后才能执行注入；若母库路径发生物理移动，需重新执行初始化以修复引用路径。

## Related Sub-Project
N/A (SOP 2.0 Core Evolution)

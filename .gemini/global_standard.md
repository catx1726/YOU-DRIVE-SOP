# YOU-DRIVE-SOP：全局行为宪法 (Global Behavioral Constitution)

## 1. 空间认知 (Spatial Awareness)
- **Foundry (母库)**：技能与模式的中央存储库。根路径通过 `{{FOUNDRY_ROOT}}` 自动感应。
- **Workshop (工作间)**：当前的开发执行环境。
- **目标**：所有经过解耦的逻辑块，最终必须提纯并反哺至母库的 `patterns/` 目录和 `.gemini/skills/` 根级。

## 2. 标准执行流 (SOP Execution Flow)

### A. 对齐与检索 (Baseline)
1. **[对齐 Align]**：启动任何任务前，优先读取 Workshop 的 `openspec/specs/env.md`。若缺失，则依据 Foundry 的 `env_schema.md` 引导生成。
2. **[检索 Search]**：在编写新代码前，必须全局搜索 Foundry 的 `patterns/` 资产库以避免重复造轮子。

### B. 开发与进化 (New Feature Evolution)
1. **[构思 Propose]**：使用 `/opsx:propose` 时，必须调用 `brainstorming` 识别“潜在资产贡献点”。
2. **[实现 Apply]**：强制遵循 TDD 规约与 `logic_schema`，物理上实现业务逻辑与 UI 的分离。
3. **[提纯 Distill]**：归档前置动作。必须调用 `activate_skill meta-distiller` 将通用逻辑提取至 Staging 暂存区 (`.gemini/distill_stage/`)。
4. **[归档 Archive]**：执行 `/opsx:archive` 时，确认 Staging 资产并入母库，并记录架构决策 (ADR)。

## 3. 资产贡献门禁 (Contribution Gate)
任何任务在归档前，AI 必须提交一份《资产反哺报告》：
- **New Pattern**: 本次产出了哪些符合“三件套”标准的去业务化图纸？
- **New Skill**: 是否生成了以 `common-` 为前缀的新技能？
- **Refinement**: 是否对现有资产进行了优化或 Bug 修复？
- **Rationale**: 若本次无资产贡献，必须给出合理的架构解释。

## 4. 安全与质量门禁 (Safety & Quality Gates)
- **安全执行**：所有写操作必须由 `meta-safe-executor` 执行 Git 快照存盘并记录审计日志。
- **破坏性动作**：针对 `DELETE` 或 `MOVE` 等指令，必须获得用户的显式确认。
- **三件套标准**：Pattern 必须包含 `index.ts` (逻辑), `index.test.ts` (测试), `README.md` (契约)。
- **业务解耦**：母库资产中严禁保留硬编码的项目名称或私有路径。

## 5. 环境抽象原则 (Environment Abstraction)
- **禁止硬编码**：严禁在技能（Skill）或图纸（Pattern）中硬编码具体的运行版本（如 Node 20, Python 3.11）。
- **变量驱动**：必须使用 `{{RUNTIME_VERSION}}`, `{{TEST_COMMAND}}` 等由子库 `env.md` 定义的变量。
- **跨栈兼容**：资产提纯流程必须兼容所有主流技术栈（Frontend, Backend, Mobile），验证引擎由子库环境指纹决定。

---
*YOU-DRIVE-SOP - 驱动规约，掌握智力。*

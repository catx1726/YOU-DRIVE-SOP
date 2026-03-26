---
name: workshop-initializing
description: Use when onboarding a Workshop to SOP 2.0 with link self-healing, multi-foundry support, and asset distillation & contribution whitelist.
mode: step-by-step
---

# Workshop Initializing (Sub-Project Alignment)

## Overview
本技能定义了子项目（Workshop）接入 SOP 2.0 的链路协议。其核心是确保子库以“链接 (Link)”方式实时共享母库资产，并在环境限制时自动回退至“拷贝 (Copy)”模式。

## Implementation Workflow (Step-by-Step)

### 0. Physical Security & Git Isolation (Mandatory)
- [ ] **物理隔离注入**：
  - **ACTION**：在子库 `.gitignore` 中强制追加忽略：`.gemini/skills/`, `.gemini/commands/`, `patterns/`, `openspec/specs/`, `ARCHITECTURE.md`, `global_standard.md`, `GETTING_STARTED.md`, `SOP_CORE_MANUAL.md`, `GEMINI.md`。
  - **VERIFICATION**：运行 `git check-ignore ARCHITECTURE.md` 确认生效。

### 1. Linking Strategy (Primary Enforcement)
- [ ] **全量资产挂载 (The Asset Manifest)**：
  - **ACTION**：AI 优先尝试建立物理链接。必须处理以下 9 个物理对象：
    1.  **DIRECTORY**: `.gemini/skills/`
    2.  **DIRECTORY**: `.gemini/commands/`
    3.  **DIRECTORY**: `patterns/`
    4.  **DIRECTORY**: `openspec/specs/`
    5.  **FILE**: `ARCHITECTURE.md`
    6.  **FILE**: `global_standard.md` (Target: `.gemini/global_standard.md`)
    7.  **FILE**: `GETTING_STARTED.md`
    8.  **FILE**: `SOP_CORE_MANUAL.md`
    9.  **FILE**: `GEMINI.md`
  - **DIRECTORY COMMAND**: `New-Item -ItemType Junction`
  - **FILE COMMAND**: `New-Item -ItemType HardLink`
  - **FALLBACK (Copy)**：若因跨分区、权限或文件系统不支持导致链接失败，AI **必须** 自动降级执行 `Copy-Item -Recurse`。
  - **REPORT**：AI **必须** 向用户明确报告物理状态：`[LINKED (实时同步)]` 或 `[COPIED (静态副本)]`。

### 2. Dashboard Activation (GEMINI.md)
- [ ] **挂载看板**：优先尝试 `HardLink` 链接母库 `GEMINI.md`。若失败则执行物理拷贝或本地化生成。

### 3. Handshake & Awareness
- [ ] **架构感知激活**：执行 `read_file ARCHITECTURE.md`。
- [ ] **注入规约意识**：向用户报告：“已建立母库映射。我已理解 SOP 2.0 的 Skeleton-Muscle 模型与 13 步生产协议。”
- [ ] **物理闭环自检**：输出 Markdown 表格，列出同步成功的规约清单。

---
*YOU-DRIVE-SOP - 驱动规约，掌握智力。*

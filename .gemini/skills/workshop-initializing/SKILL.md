---
name: workshop-initializing
description: Use when onboarding a Workshop to SOP 2.0 with link self-healing, multi-foundry support, and asset distillation & contribution whitelist.
mode: step-by-step
---

# Workshop Initializing (Sub-Project Alignment)

## Overview
本技能定义了子项目（Workshop）接入 SOP 2.0 的链路协议。其核心是确保子库以“链接 (Link)”方式实时共享母库智力资产，并自动实施 Git 物理隔离。

## Implementation Workflow (Step-by-Step)

### 0. Physical Security & Git Isolation (Mandatory)
- [ ] **物理隔离注入**：
  - **ACTION**：检测子库根目录 `.gitignore`。
  - **INJECTION**：物理追加（防止 Git 穿透删除）：
    ```text
    # YOU-DRIVE-SOP Physical Links
    .gemini/skills/
    .gemini/commands/
    patterns/
    openspec/specs/
    .gemini/link.json
    ARCHITECTURE.md
    global_standard.md
    GETTING_STARTED.md
    SOP_CORE_MANUAL.md
    ```
  - **VERIFICATION**：运行 `git check-ignore ARCHITECTURE.md` 确认生效。

### 1. Linking Strategy (Physical Enforce)
- [ ] **全量资产链接**：
  - **ACTION**：AI 必须为以下目录/文件物理建立 Junction/Symlink：
    - `.gemini/skills/`
    - `.gemini/commands/`
    - `patterns/`
    - `openspec/specs/`
    - `ARCHITECTURE.md`
    - `global_standard.md`
    - `GETTING_STARTED.md`
    - `SOP_CORE_MANUAL.md`
  - **Fallback**：仅当物理环境不支持链接时，方可进行静态 Copy。
  - **REPORT**：AI **必须**向用户明确报告：`[LINKED (实时同步)]` 或 `[COPIED (静态副本)]`。

### 2. Handshake & Awareness
- [ ] **架构感知激活**：执行 `read_file ARCHITECTURE.md`。
- [ ] **注入规约意识**：向用户报告：“已建立母库链接。我已理解 SOP 2.0 的 Skeleton-Muscle 模型与 13 步生产协议。”
- [ ] **物理闭环自检**：输出 Markdown 表格，列出当前子库已通过链接感知的全量规约清单。

---
*YOU-DRIVE-SOP - 驱动规约，掌握智力。*

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
    GEMINI.md
    ```
  - **VERIFICATION**：运行 `git check-ignore ARCHITECTURE.md` 确认生效。

### 1. Linking Strategy (Primary Enforcement)
- [ ] **全量资产挂载 (The Asset Manifest)**：
  - **ACTION**：AI 优先尝试建立物理链接。必须处理以下 9 个物理对象：
    1.  **DIRECTORY**: `.gemini/skills/`
    2.  **DIRECTORY**: `.gemini/commands/`
    3.  **DIRECTORY**: `patterns/`
    4.  **DIRECTORY**: `openspec/specs/`
    5.  **FILE**: `ARCHITECTURE.md`
    6.  **FILE**: `global_standard.md`
    7.  **FILE**: `GETTING_STARTED.md`
    8.  **FILE**: `SOP_CORE_MANUAL.md`
    9.  **FILE**: `GEMINI.md`
  - **DIRECTORY COMMAND**: `New-Item -ItemType Junction`
  - **FILE COMMAND**: `New-Item -ItemType HardLink`
  - **FALLBACK (Copy)**：若因跨分区、权限或文件系统不支持导致链接失败，AI **必须** 自动降级执行 `Copy-Item -Recurse`。
  - **REPORT**：AI **必须** 向用户明确报告物理状态：`[LINKED (实时同步)]` 或 `[COPIED (静态副本)]`。

### 2. Identity Injection (Workshop Status)
- [ ] **物理身份写入**：在子库根目录创建 `role.json`。
  - **CONTENT**: `{"role": "workshop", "foundry_link": "{{FOUNDRY_ROOT}}", "status": "operational"}`
- [ ] **AI 身份觉醒**: AI 在启动会话时，**必须**首先读取 `role.json`。
- [ ] **角色报告 (Mandatory)**：若检测到 `role: "workshop"`，AI **必须**向用户物理确认：“我当前位于 Workshop 子库，通过 Junction 挂载了母库资产，已准备好执行标准 SOP 2.0 任务。”

### 3. Final Synthesis & Handover
- [ ] **物理重载 (Force Registry Reload)**: AI **必须**告知用户：『初始化完成，为了使新的 Skill 和 Command 生效，请物理重启会话 (运行 `/exit` 后重新执行 `gemini`)。』
- [ ] **规约审计清单**：输出 Markdown 表格，列出当前子库已通过链接感知的全量规约清单。
- [ ] **交互式引导**：询问：『您是想：A) 扫描旧项目 (提纯) 还是 B) 开发新功能 (Apply)？』

---
*YOU-DRIVE-SOP - 驱动规约，掌握智力。*

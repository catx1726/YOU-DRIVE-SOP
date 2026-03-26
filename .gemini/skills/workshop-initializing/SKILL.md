---
name: workshop-initializing
description: Use when onboarding a Workshop to SOP 2.0 with link self-healing, multi-foundry support, and asset distillation & contribution whitelist.
mode: step-by-step
---

# Workshop Initializing (Sub-Project Alignment)

## Overview
本技能定义了子项目（Workshop）接入 SOP 2.0 的链路协议。其核心是确保子库能够识别母库（Foundry）的规范指纹，并精准上报可收割的高价值资产。

## Implementation Workflow (Step-by-Step)

### 0. Git Isolation Sentinel (Physical Safety Gate)
**⚠️ [极高风险警告]**：在子库未配置 `.gitignore` 的情况下建立 Junction 链路，会导致 Git 切换分支时物理删除母库源文件。

- [ ] **物理隔离注入**：
  - **ACTION**：检测子库根目录是否存在 `.gitignore`。
  - **INJECTION**：物理追加：`.gemini/skills/`, `.gemini/commands/`, `patterns/`, `.gemini/link.json`。
  - **VERIFICATION**：执行 `git check-ignore .gemini/skills/`。

### 1. Toolchain Pre-check
- [ ] **OpenSpec & GitHub CLI 探测**：检查 `openspec` 和 `gh` 版本，验证 `gh auth status`。

### 2. Config Injection & Foundry Root Discovery
- [ ] **物理链路挂载**：
  - **ACTION**：建立物理链路 (Junction)。
  - **物理清单**：
    - `openspec\config.yaml`: 深度合并。
    - `openspec\schemas\` & `openspec\specs\`。
    - `GEMINI.md`, `ARCHITECTURE.md`, `GETTING_STARTED.md`, `global_standard.md`。
    - **同步指令集**：`.gemini\commands\` (自动化 `/opsx` 指令)。
    - **同步智力库**：`.gemini\skills\` & `patterns/`。

### 3. Workflow Alignment
- [ ] **建立作业空间**：初始化 `logic.md` 与本地 `decisions/`。
- [ ] **GitHub 协作注入**：创建 `PULL_REQUEST_TEMPLATE.md`。

### 4. Logic Handshake
- [ ] **物理通读架构**：执行 `read_file ARCHITECTURE.md`。
- [ ] **注入规约意识**：报告已理解“Skeleton-Muscle”模型。

### 5. Final Synthesis
- [ ] **物理链路状态汇报**：明确当前是 **Linked (实时同步)** 还是 **Copied (静态副本)**。
- [ ] **规约审计清单 (Spec Audit)**：输出 Markdown 表格，列出同步成功的规约。
- [ ] **交互式引导**：询问下一步行动。

---
*YOU-DRIVE-SOP - 驱动规约，掌握智力。*

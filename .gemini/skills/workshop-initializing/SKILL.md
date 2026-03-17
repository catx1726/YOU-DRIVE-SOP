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
**⚠️ [极高风险警告]**：在子库未配置 `.gitignore` 的情况下建立 Junction 链路，会导致 Git 切换分支时物理删除母库源文件。AI **必须**在执行任何物理链接前执行此步骤。

- [ ] **物理隔离注入**：
  - **ACTION**：检测子库根目录是否存在 `.gitignore`。
  - **INJECTION**：若不存在则创建；若已存在，AI **必须**物理追加以下规则：
    ```text
    # YOU-DRIVE-SOP Physical Links
    .gemini/skills/
    patterns/
    .gemini/link.json
    ```
  - **VERIFICATION**：执行 `git check-ignore .gemini/skills/` 确认隔离已生效。若未生效，严禁执行下一步。

### 1. Toolchain & Runtime Pre-check
- [ ] **OpenSpec & GitHub CLI 探测**：
  - **ACTION**：检查 `openspec --version` 和 `gh --version`。
  - **AUTH CHECK**：执行 `gh auth status`。
- [ ] **Windows 权限预检 (Junction Permission)**：
  - **ACTION**：尝试创建一个临时 Junction 验证权限。
  - **RECOVERY (Error 5)**：若报错 `Access Denied`，AI **必须**停止执行并提示：
    > **⚠️ [权限被拒绝]**
    > 检测到 Windows 权限限制。请执行以下任一操作：
    > 1. 开启 **Windows 开发者模式**（设置 > 隐私和安全性 > 开发人员）。
    > 2. 以 **管理员身份** 重新启动命令行窗口。

### 2. Config Injection & Foundry Root Discovery
- [ ] **Foundry Root 感应 (Path Normalization)**：
  - **ACTION**：AI 探测母库路径后，**必须**执行物理绝对路径转换（如 `Resolve-Path`），严禁在 `link.json` 中存储相对路径。
- [ ] **OpenSpec 初始化与补丁**：
  - **ACTION**：执行 `openspec init` (如果 `openspec/config.yaml` 不存在)。
  - **PATCH**：读取母库的 `{{FOUNDRY_ROOT}}\openspec\config_foundry.yaml`。
- [ ] **物理链路挂载 (Link-First, Copy-Fallback)**：
  - **TRY (Junction)**：执行 `gemini skills link {{FOUNDRY_ROOT}}\.gemini\skills --scope workspace --consent`。
  - **IDENTIFY**：检查 `.gemini/skills` 的物理属性。
  - **FALLBACK (Copy)**：若属性非 `ReparsePoint`（说明链接未建立，回退成了复制），AI **必须**执行以下动作：
    1. 物理拷贝母库的 `patterns/` 目录至子库（若链接也失效）。
    2. 在 `link.json` 中记录 `{"link_type": "copy"}`。
    3. 在后续报告中发出 **[智力继承断裂]** 警告。
- [ ] **创建 link.json**：存储归一化后的绝对路径 `{"foundry_root": "{{RESOLVED_ABS_PATH}}", "link_type": "junction|copy"}`。

### 3. Environmental & Spec Alignment
- [ ] **规约全量同步 (The Full Spec Sync)**：
  - **ACTION**：递归物理拷贝母库的以下资产至子库：
    - `{{FOUNDRY_ROOT}}\openspec\specs\` -> `openspec\specs\`
    - `{{FOUNDRY_ROOT}}\openspec\schemas\` -> `openspec\schemas\`
    - `{{FOUNDRY_ROOT}}\openspec\specs\foundry-protocols\` -> `openspec\specs\foundry-protocols\`
    - **GLOBAL ASSETS**：物理拷贝母库根目录下的 `global_standard.md`, `AGENTS.md`, `GETTING_STARTED.md` 至子库根目录。
  - **SAFETY**：同步前确认子库已执行 Git 快照。
- [ ] **环境指纹扫描**：执行本地 `package.json` 与 `node -v` 扫描。
- [ ] **偏差报告生成**：在 `openspec/specs/env.md` 中标注架构代沟，并定义高价值资产沉淀白名单。

### 4. Sub-Project Workspace Initialization
- [ ] **建立作业空间**：创建 `openspec/specs/logic.md` 与本地 `decisions/` 目录。
- [ ] **GitHub 协作注入**：
  - **ACTION**：在子库 `.github/` 目录下创建 `PULL_REQUEST_TEMPLATE.md`。
  - **CONTENT**：
    ```markdown
    ## Summary
    <!-- 简述本次变更意图 -->

    ## Knowledge Points
    - **Arch Decision**: 引用 openspec/decisions 下的 ADR。
    - **Asset Contribution**: 本次反哺了哪些 Pattern？

    ## Closure
    Closes #ISSUE_ID
    ```

### 5. Foundry Manual Alignment (Contract Handshake)
- [ ] **物理通读母库手册**：AI 必须执行 `read_file {{FOUNDRY_ROOT}}/SOP_CORE_MANUAL.md`。
- [ ] **注入规约意识**：AI 必须向用户报告：『已同步母库 SOP 2.0 规约。我已理解“逻辑刚性”、“资产循环”与“人机协作协议”。』

### 6. Dashboard Standard Injection
- [ ] **生成看板式 GEMINI.md**：在子库根目录生成包含「🚀 快速操作看板」的 `GEMINI.md`。
- [ ] **注入内容模板**：
  ```markdown
  # 🚀 YOU-DRIVE-SOP 快速操作看板 (Workshop)

  > **"AI 驱动逻辑，你驱动规约。"**

  当前已链接母库：`{{FOUNDRY_ROOT}}`
  物理链路类型：`{{LINK_TYPE}}`

  ## 🚥 12 步生产生命周期
  所有的开发任务 **必须** 严格遵循 [**12 步工业级操作协议**](./GETTING_STARTED.md#🚦-生产生命周期-the-12-step-protocol)：
  `Issue -> Branch -> Propose -> Apply -> Verify -> Distill -> Archive -> Merge`

  ## 常用指令集
  ### 场景 A：新功能开发 (Feature)
  - `/opsx:propose "功能名称"` —— 发起新功能提案。
  - `/opsx:apply` —— 按照 `tasks.md` 步进执行任务。
  - `/opsx:verify` —— 物理核对规格 Scenario 是否达成。

  ### 场景 B：资产提纯与维护 (Maintenance)
  - `activate_skill meta-distiller` —— 执行逻辑提取与参数化。
  - `activate_skill workshop-sync` —— **[Copied 模式专用]** 拉取母库最新更新。
  - `/opsx:archive` —— 执行智力资产反哺并归档变更。

  ## 🚦 状态查询指令
  您可以随时向 AI 发起以下查询，以确认物理对齐状态：
  - 『**目前的初始化状态如何？**』 —— AI 将检查链路、宪法与协议的完整性。
  - 『**我接下来该做什么？**』 —— AI 将根据 `ops_changelog.md` 和 `tasks.md` 给出下一步建议。

  ## 行为约束
  - 所有的 AI 操作必须遵循 [母库全局标准](./global_standard.md) 与 [代理协议](./AGENTS.md)。
  ```

### 6. Final Synthesis & Interactive Handover
- [ ] **终期质量审计**：
  - **ACTION**：通读初始化产物（env.md, link.json, GEMINI.md），确保路径正确。
  - **物理链路状态汇报**：AI **必须** 根据 `link.json` 记录，明确告知用户当前是 **Linked (实时同步)** 还是 **Copied (静态副本)** 模式。
  - **规约审计清单 (Spec Audit)**：AI 必须扫描 `openspec/specs/` 目录，并向用户输出 Markdown 表格，列出所有已从母库同步成功的规约（包含目录名与 spec.md 存在状态）。
- [ ] **交互式引导**：AI 必须询问：『✓ 初始化已完成！您现在是想：A) 扫描旧项目（输入 A）还是 B) 开发新功能（输入 B）？』

## 链接自愈协议 (Link Self-Healing)
当用户请求“刷新技能”、“同步母库”或“修复链接”时，必须执行以下幂等操作：
1. **识别环境**：确认 Target 和 Source 路径。
2. **清理失效引用**：安全删除所有属性为 `ReparsePoint` 的文件夹。
3. **重建引用**：重新建立 Junction 映射。

## Common Mistakes & Red Flags
- **忽略 .gitignore**：未将链接文件夹加入忽略名单，导致 Git 穿透删除。
- **链路不匹配**：`link.json` 路径与实际挂载路径不一致。
- **环境污染**：未对逻辑进行白名单过滤。

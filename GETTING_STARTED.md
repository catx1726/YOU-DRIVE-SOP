# YOU-DRIVE-SOP 2.0 工业级操作手册

> **"Standardization, Specification, Process, Automation, Sharing."**

本手册定义了 YOU-DRIVE-SOP 2.0 体系下的标准基础设施搭建与 12 步生产生命周期。

---

## 基础设施搭建 (Foundry & Workshop Setup)

1.  **Clone 本库 (母库)**：
    ```bash
    git clone git@github.com:catx1726/YOU-DRIVE-SOP.git foundry
    ```
2.  **全局安装 OpenSpec**：
    ```bash
    npm install -g @fission-ai/openspec@latest
    ```
3.  **子库初始化引擎**：进入业务项目，执行： `bash     openspec init     ` _✓ 物理产出：生成 `openspec/config.yaml`（初始为空白文件）。_

4.  **物理自举链接**：由于子库尚未链接母库，AI 此时无法感知技能。您**必须**手动执行以下指令来建立初步联系： `bash     gemini skills link <FOUNDRY_PATH>/.gemini/skills --scope workspace --consent     ` _注：`<FOUNDRY_PATH>` 是您在第 1 步中 Clone 的母库绝对路径。_

### 🧱 物理安全红线 (Safety Gate)

**在执行下一步前，请确保子库已配置 `.gitignore`。** 若子库使用 Git 管理，**必须**忽略以下路径：

- `.gemini/skills/`
- `patterns/`
- `.gemini/link.json` _⚠️ 警告：如果不配置忽略规则，Git 在切换分支时可能会尝试删除这些物理链路，并极易穿透链路导致母库源文件被物理销毁。_

4.  **子库物理对齐 (Handshake)**：在子库执行： `bash     activate_skill workshop-initializing     `

        _✓ 逻辑：建立物理链路 (Junction)，将母库的以下资产挂载至子库：_
        - `openspec\config.yaml`：读取母库 `config_foundry.yaml` 并 Deep Merge。
        - `openspec\schemas\`：同步全量协议模板。
        - `openspec\specs\`：递归同步全量治理规约。
        - `GEMINI.md`：注入「🚀 快速操作看板」。
        - `AGENTS.md` & `global_standard.md`：同步代理定义与物理宪法。
        - `.gemini\skills` & `patterns/`：挂载全量技能与图纸库。
        - _链路存根：生成 `.gemini/link.json` 记录母库物理绝对路径。_

---

## 生产生命周期 (The 13-Step Protocol)

**标准流 (13-Step Abstract Flow):** `Launch -> Issue -> Branch -> Propose -> Apply -> TDD -> Safety-Audit -> Verify -> Distill -> Archive -> PR -> Merge -> Close`

1.  **需求探索 (Brainstorm)**：执行 `activate_skill brainstorming`。识别业务逻辑中的“资产贡献点”。
2.  **需求固化 (Issue)**：使用 `gh issue create` 创建 Issue，记录原始需求并获得唯一 ID。
3.  **分支隔离 (Branch)**：执行 `git checkout -b issue-N` (或 `task/N`)，**严禁**在 `main` 分支执行任何开发。
4.  **提案 (Propose)**：执行 `/opsx:propose`，激活 `writing-plans` 技能，生成 `tasks.md`，并确保包含强制性的“规约与环境自检”步骤。
5.  **执行内环 (Apply-Act)**：执行 `/opsx:apply`，激活 `executing-plans` 技能读取 `tasks.md` 按序执行任务。
6.  **TDD 循环 (Test)**：在执行每个任务时，激活 `test-driven-development`，执行“红-绿-重构”测试循环。
7.  **安全审计 (Audit)**：任何文件修改前激活 `meta-safe-executor`，在 `.gemini/ops_changelog.md` 中物理留痕。
8.  **自我验证 (Verification)**：激活 `verification-before-completion`，在提交前产出验证证据（Logs/Diff）。
9.  **规约验证 (Verify)**：执行 `/opsx:verify`。系统将首先执行 `openspec/config.yaml` 定义的 `test_command`，通过后再执行手动的规约比对。
10. **资产提纯 (Distill)**：**[归档前置]** 激活 `activate_skill meta-distiller`，将通用逻辑脱水提取至 `.gemini/distill_stage/`。
11. **归档 (Archive)**：使用 `/opsx:archive` 固化本次变更记录，并激活 `writing-skills` 将提纯成果转化为新的母库技能。
12. **发起评审 (PR)**：使用 `gh pr create` 发起评审，等待 CI/CD 自动通过 `pr_summary.yml` 的合规性校验。
13. **闭环 (Merge/Close)**：使用 `gh pr merge` 合并代码，`gh issue close` 关闭 Issue。

---

## 日常维护 (Daily Maintenance)

### 同步母库最新智力 (Foundry Sync)

如果您处于 **Copied (静态副本)** 模式，或者母库发布了新的元规约，请执行以下指令进行增量对齐：

```bash
activate_skill workshop-sync
```

_✓ 物理逻辑：系统将从 `link.json` 定义的路径执行增量拉取（`xcopy /D`），仅更新较新或缺失的 Skills 和 Patterns，不会破坏您的本地业务代码。_

---

## 故障排除 (Troubleshooting)

### 1. Windows 权限错误 (Access Denied / Error 5)

在执行 `workshop-initializing` 建立物理链路时，若遇到权限报错：

- **原因**：Windows 限制非管理员创建符号链接。
- **方案**：进入 Windows **设置 > 隐私和安全性 > 面向开发人员**，开启 **“开发人员模式”**。

### 2. 路径感应失败 (Path Discovery)

若 AI 无法自动定位母库：

- **方案**：手动在子库根目录创建 `.gemini/link.json`，内容为：`{"foundry_root": "C:\\绝对路径\\TO\\FOUNDRY"}`。

---

## 递归模式与母库自演进 (Recursive Mode & Self-Evolution)

当您作为**母库管理员**需要修改母库本身的 Skills、Patterns 或治理规约时，系统支持将其作为自身的 Workshop 进行自演进。

### 1. 配置本地母库为同步源

在母库根目录的 `.gemini/link.json` 中，确保路径指向自身（或在环境变量中定义）：

```json
{
  "foundry_root": "."
}
```

或使用绝对路径。

### 2. 自演进操作流程

在母库中执行变更时，**必须**遵循标准的 12 步协议，特别是：

1. **Propose**: 使用 `/opsx:propose` 提交架构或技能变更提案。
2. **Apply**: 在本地执行修改。
3. **TDD**: 确保新编写的 Skill 或 Pattern 通过本地测试。
4. **Distill & Archive**: 执行归档，将变更正式并入母库资产池。

### 3. 陷阱规约 (Safety Guardrails)

- **循环引用**: 在递归模式下执行 `workshop-sync` 时，系统会自动识别源与目标一致并跳过物理拷贝，以防文件损坏。
- **分支隔离**: 即使是自演进，也严禁在 `main` 分支直接修改 `skills/`，必须通过 `issue-N` 分支进行治理流转。

---

_YOU-DRIVE-SOP - 驱动规约，掌握智力。_

# YOU-DRIVE-SOP 快速入门指南

欢迎使用 **YOU-DRIVE-SOP** 框架。本指南将带您完成从基础环境搭建到实战开发沉淀的全过程。

## 🏁 快速启动 (Quick Start)

### 0. AI 登舰自检 (AI Onboarding) —— **关键第一步**
当您克隆本项目并在本地启动 Gemini CLI 时，请立即输入以下指令，让 AI 引擎对齐您的规约：
> 『请总结 `SOP_CORE_MANUAL.md` 的核心逻辑，并执行一次母库物理健康自检报告。』

---

## 🏗️ 基础设施搭建 (Foundry Setup)

**Foundry** 是您的中央“智力库”，存储着所有项目共享的 Skills (技能) 与 Patterns (图纸)。

1. **克隆并进入目录**：
   ```bash
   git clone https://github.com/catx1726/YOU-DRIVE-SOP.git my-foundry
   cd my-foundry
   ```

2. **内容化初始化**：
   ```bash
   activate_skill foundry-initializing
   ```
   *✓ 效果：自动创建目录并注入全局宪法与协议模板。*

---

## 🚦 实战路径 A：旧项目逆向提纯 (Legacy Distillation)

**目标**：接手一个没有任何 SOP 记录的旧项目，将其中的高价值代码收割至母库。

1. **进入子项目目录**：
   ```bash
   cd /path/to/legacy-project
   ```

2. **建立物理链路**：
   ```bash
   gemini skills link /path/to/my-foundry/.gemini/skills --scope workspace --consent
   ```

3. **对齐初始化**：
   ```bash
   activate_skill workshop-initializing
   ```
   *✓ 效果：识别技术栈，生成 link.json 并自动注入 GEMINI.md 标准。*

4. **开启逆向识别**：
   ```bash
   activate_skill legacy-extractor
   ```
   *✓ 指令链：识别基因 -> 扫描路径 -> 定位逻辑。*

5. **执行原子提纯**：
   当识别到 `src/utils/math.ts` 具有通用价值时：
   ```bash
   activate_skill meta-distiller
   ```
   *✓ 效果：在本地生成 .gemini/distill_stage/ 包含代码、测试与 Skill 描述。*

6. **归档反哺**：
   ```bash
   /opsx:archive
   ```
   *✓ 效果：确认暂存资产并入母库，清理本地审计日志。*

---

## 🚦 实战路径 B：新功能开发闭环 (New Feature Evolution)

**目标**：在一个已链接母库的项目中开发新功能，并确保产物即资产。

1. **发起变更提案**：
   ```bash
   /opsx:propose add-api-cache
   ```
   *AI 将自动触发 brainstorming 并依据 foundry-protocols 生成任务列表。*

2. **纪律化实施 (TDD)**：
   ```bash
   /opsx:apply
   ```
   *AI 将优先编写测试，确保逻辑与 UI 分离。*

3. **任务终期提纯**：
   在开发接近尾声时：
   ```bash
   activate_skill meta-distiller
   ```
   *✓ 效果：从 add-api-cache 任务中提取通用缓存逻辑。*

4. **归档并合并资产**：
   ```bash
   /opsx:archive
   ```
   *✓ 效果：记录 ADR，任务快照归档，新资产正式进入母库。*

---

## 🛡️ 驾驶员守则

- **始终 Git 优先**：确保您的工作区在 Git 管理下，`meta-safe-executor` 才能为您提供 100% 的回滚保障。
- **拒绝硬编码**：在编写 Skill 时，请始终使用 `{{FOUNDRY_ROOT}}` 占位符。
- **先审批后入库**：在 `distill_stage` 中多看一眼，确保每一份进入母库的资产都是纯净的。

*Happy Distilling & Contributing!*

---

## 🛠️ 故障排除 (Troubleshooting)

### Windows 环境下 "Access Denied (Error 5)" 错误
如果在执行 `gemini skills link` 时遇到权限错误，这通常是因为 Windows 限制了非管理员创建物理链路的能力。

**解决方案**：
1. **开启开发者模式（推荐）**：
   - 进入 Windows **设置** > **隐私和安全性** > **面向开发人员**。
   - 开启 **“开发人员模式”**。这将允许在无需管理员权限的情况下创建符号链接。
2. **管理员权限运行**：
   - 右键点击终端图标（PowerShell/CMD/Terminal），选择 **“以管理员身份运行”**。
3. **安全软件白名单**：
   - 确保您的杀毒软件未拦截 `powershell.exe` 的 `New-Item` 操作。

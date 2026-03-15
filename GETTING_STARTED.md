# YOU-DRIVE-SOP 驾驶员入门指南 (Quick Start)

> **"Welcome to the Cockpit. AI drives logic, YOU drive protocols."**

本指南将根据您的物理身份（母库管理员或业务开发者），引导您快速进入 SOP 2.0 执行流。

---

## 🧭 路径选择：您是谁？

### 🛤️ 路径 A：实验室管理员 (Foundry Manager)
**目标**：建立智力母库，定义全局规约，沉淀原子技能与模式图纸。

1. **初始化母库**：
   ```bash
   activate_skill foundry-initializing
   ```
   *✓ 效果：物理生成 .gemini/global_standard.md 与 openspec/ 核心规约种子。*

2. **管理智力资产**：
   - 在 `patterns/` 中维护通用代码图纸。
   - 在 `.gemini/skills/` 中维护 AI 操作规约。

---

### 🛤️ 路径 B：资产收割员 (Asset Harvester)
**目标**：在具体业务项目中引用母库，通过任务开发收割高价值逻辑并反哺。

1. **对齐初始化**：
   ```bash
   activate_skill workshop-initializing
   ```
   *✓ 效果：建立物理链路 (Junction)，同步母库全量规约，生成项目看板。*

2. **发起任务提案**：
   ```bash
   /opsx:propose "feature-name"
   ```
   *✓ 效果：自动创建 Issue 分支并生成带自检项的任务列表。*

3. **任务终期提纯**：
   ```bash
   activate_skill meta-distiller
   ```
   *✓ 效果：将业务逻辑转化为通用 Pattern 暂存。*

4. **归档反哺**：
   ```bash
   /opsx:archive
   ```
   *✓ 效果：将资产正式并入母库，生成 PR 摘要。*

---

## 🛠️ 故障排除 (Troubleshooting)

### 1. Windows 权限错误 (Access Denied / Error 5)
在执行 `workshop-initializing` 建立物理链路时，若遇到权限报错：
- **原因**：Windows 限制非管理员创建符号链接。
- **方案**：进入 Windows **设置 > 隐私和安全性 > 面向开发人员**，开启 **“开发人员模式”**。

### 2. 路径感应失败 (Path Discovery)
若 AI 无法自动定位母库：
- **方案**：手动在子库根目录创建 `.gemini/link.json`，内容为：`{"foundry_root": "C:\\绝对路径\\TO\\FOUNDRY"}`。

---
*YOU-DRIVE-SOP - 驱动规约，掌握智力。*

---
name: workshop-initializing
description: Use when onboarding a Workshop to SOP 2.0 with link self-healing, multi-foundry support, and asset distillation & contribution whitelist.
mode: step-by-step
---

# Workshop Initializing (Sub-Project Alignment)

## Overview
本技能定义了子项目（Workshop）接入 SOP 2.0 的链路协议。其核心是确保子库能够识别母库（Foundry）的规范指纹，并精准上报可收割的高价值资产。

## Implementation Workflow (Step-by-Step)

### 1. Link Establishing
- [ ] **物理链路挂载**：执行 `gemini skills link {{FOUNDRY_ROOT}}\.gemini\skills --scope workspace --consent`。
- [ ] **创建 link.json**：在子库根目录写入母库绝对路径存根 `{"foundryPath": "{{FOUNDRY_ROOT}}"}`。

### 2. Environmental & Spec Alignment
- [ ] **规约影子同步**：同步母库 `{{FOUNDRY_ROOT}}\openspec\schemas\` 和 `{{FOUNDRY_ROOT}}\openspec\specs\foundry-protocols\` 至子库。
- [ ] **环境指纹扫描**：执行本地 `package.json` 与 `node -v` 扫描。
- [ ] **偏差报告生成**：在 `openspec/specs/env.md` 中标注架构代沟，并定义高价值资产沉淀白名单（后续由 `meta-distiller` 执行）。

### 3. Sub-Project Workspace Initialization
- [ ] **建立作业空间**：创建 `openspec/specs/logic.md` 与本地 `decisions/` 目录。

### 4. Standard Injection
- [ ] **注入行为宪法**：在子库根目录生成引用母库 `{{FOUNDRY_ROOT}}\.gemini\global_standard.md` 的 `GEMINI.md`。

### 5. Final Synthesis
- [ ] **终期质量审计**：通读初始化产物（env.md, link.json, GEMINI.md），检查路径正确性与标准对齐度，确保无分步导致的细节遗漏。

## 链接自愈协议 (Link Self-Healing)
当用户请求“刷新技能”、“同步母库”或“修复链接”时，必须执行以下幂等操作：
1. **识别环境**：确认 Target 和 Source 路径。
2. **清理失效引用**：安全删除所有属性为 `ReparsePoint` 的文件夹。
3. **重建引用**：重新建立 Junction 映射。

## Common Mistakes & Red Flags
- **跳过分步确认**：忽略 `mode: step-by-step` 一次性执行。
- **链路不匹配**：`link.json` 路径与实际挂载路径不一致。
- **环境污染**：未对逻辑进行白名单过滤。

---
name: foundry-initializing
description: Use when establishing the central SOP 2.0 laboratory (Foundry) to manage cross-project assets, evolution schemas, and core behavioral standards with self-evolution loops.
mode: step-by-step
---

# Foundry Initializing (SOP 2.0 Foundry)

## Overview
本技能定义了“SOP 2.0 母库”的基座结构与自演进闭环。母库作为中央实验室，负责资产的“去业务化提纯”与“元能力（Meta-Skills）”的持续迭代。

## Implementation Workflow (Step-by-Step)

### 1. Structure Initialization
- [ ] **建立核心层**：创建 `.gemini/skills/` (meta, common) 与 `openspec/` (schemas, decisions)。
- [ ] **建立资产层**：创建 `patterns/` 代码图纸目录。

### 2. Standard & Constitution
- [ ] **生成全局标准**：创建 `.gemini/global_standard.md` 并注入执行流规约。
- [ ] **生成协议模板**：在 `openspec/schemas/` 下建立 env, logic, decision 初始模板。

### 3. Verification & Synthesis
- [ ] **物理扫描**：执行 `tree` 验证目录树完整性。
- [ ] **指令测试**：确认 `activate_skill` 能正确加载扁平化技能库。
- [ ] **终期质量审计**：通读生成的标准与协议，确保逻辑一致性与字数厚度符合 SOP 2.0 工业基准。

## Red Flags
- 物理隔离层缺失或命名不规范。
- 擅自修改 `global_standard.md` 而未记录 ADR。
- 在 `mode: step-by-step` 模式下跳过用户确认。

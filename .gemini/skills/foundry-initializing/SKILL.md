---
name: foundry-initializing
description: Use when establishing the central SOP 2.0 laboratory (Foundry) to manage cross-project assets, evolution schemas, and core behavioral standards with self-evolution loops.
mode: step-by-step
---

# Foundry Initializing (SOP 2.0 Foundry)

## Overview
本技能负责初始化 **YOU-DRIVE-SOP** 的中央母库（Foundry）。不同于传统的物理建档，本初始化流程采用“内容驱动”模式，在创建目录的同时，自动注入框架预置的全局标准（Constitution）与生产协议（Schemas）。

## Implementation Workflow (Step-by-Step)

### 0. Upstream Deep-Dive (Source-Level Alignment)
- [ ] **探测上游引擎**：自动检查 `tools/OpenSpec/` 与 `tools/superpowers/` 物理目录。
- [ ] **物理通读规约**：AI 必须执行 `read_file` 动作，通读 `tools/OpenSpec/schemas/` 下的 `.yaml` 定义与 `tools/superpowers/skills/` 的目录结构。
- [ ] **同步智力血统**：AI 必须向用户总结当前本地上游引擎的版本特性，并确认母库的 `openspec/schemas/` 与上游标准 100% 物理兼容。

### 1. Structure Initialization
- [ ] **建立物理基座**：创建 `.gemini/skills/`、`openspec/decisions/`、`openspec/schemas/` 以及 `patterns/` 目录。
- [ ] **物理去冗余**：确保 `skills/` 下无 `meta/` 或 `common/` 等二级目录，维持扁平化架构。

### 2. Standard & Constitution Injection
- [ ] **注入全局行为宪法**：创建 `.gemini/global_standard.md`，并同步注入 `YOU-DRIVE-SOP` 预置的中文版“对齐-检索-提纯-演进”执行流规约。
- [ ] **注入协议模板**：在 `openspec/schemas/` 下同步生成 `env_schema.md` (环境)、`logic_schema.md` (提纯)、`decision_schema.md` (决策) 的工业级模板。

### 3. Verification & Synthesis
- [ ] **物理扫描**：执行 `tree` 验证目录树完整性。
- [ ] **指令测试**：确认 `activate_skill` 能正确加载扁平化后的技能库。
- [ ] **终期质量审计**：通读生成的标准与协议，确保逻辑闭环且字数厚度符合开源框架标准。

### 4. AI Context Onboarding (The Chain Connection)
- [ ] **物理探测手册**：自动探测根目录是否存在 `SOP_CORE_MANUAL.md`。
- [ ] **主动报告与分析**：若手册存在，AI 必须在初始化完成后，自动为用户总结手册中的 **“第一章：逻辑刚性”**，并提示用户：『初始化已完成，我已通过核心手册对齐了 SOP 2.0 规约。您现在可以开始“资产反哺”之旅。』

## Red Flags
- 初始化产生空文件（必须包含实质性规约内容）。
- 擅自创建 `meta/` 或 `common/` 等无法被 CLI 直接加载的物理嵌套目录。
- 在 `mode: step-by-step` 模式下未获得用户确认即执行。

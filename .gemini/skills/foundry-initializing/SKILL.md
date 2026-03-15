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
- [ ] **物理对齐规约**：AI 优先读取 `openspec/specs/upstream-lineage/` 目录下的 `openspec-core.md` 与 `superpowers-core.md`。
- [ ] **源码溯源（按需）**：若上述规约缺失，则必须深入 `tools/OpenSpec/src/` 与 `tools/superpowers/skills/` 通读源码。
- [ ] **同步智力血统**：AI 必须向用户总结当前对上游引擎核心逻辑（如卡恩算法、TDD 物理删除）的对齐状态。

### 1. Structure & Core Config Generation
- [ ] **建立物理基座**：创建 `.gemini/skills/`、`openspec/decisions/`、`openspec/schemas/` 以及 `patterns/` 目录。
- [ ] **生成母库全局配置**：若 `openspec/config_foundry.yaml` 缺失，AI 必须基于 SOP 2.0 标准物理创建。
- [ ] **物理去冗余**：确保 `skills/` 下无 `meta/` 或 `common/` 等二级目录，维持扁平化架构。

### 2. Standard & Protocol Template Injection
- [ ] **注入全局行为宪法**：创建 `.gemini/global_standard.md`。若已存在，AI 必须执行 `read_file` 检查是否包含“提纯-反哺”核心规约，并进行增量补丁。
- [ ] **物理生成协议模板**：在 `openspec/schemas/` 下**物理创建**以下模板：
  - `env_schema.md`: 定义环境指纹识别标准。
  - `logic_schema.md`: 定义“三件套”资产准入标准。
  - `decision_schema.md`: 定义 ADR 决策记录格式。
- [ ] **同步生产协议**：创建 `openspec/specs/foundry-protocols/spec.md`，定义资产收割的物理规则。

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

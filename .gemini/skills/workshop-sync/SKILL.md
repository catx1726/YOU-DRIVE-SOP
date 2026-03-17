---
name: workshop-sync
description: Use to manually pull the latest Skills and Patterns from the Foundry to a Copied Workshop.
---

# Workshop Sync (Intelligence Pull Protocol)

## Overview
当子库由于权限或环境限制采用 **Copied (静态副本)** 模式时，智力继承的实时链路已失效。本技能提供了一套安全的物理同步机制，允许用户主动从母库拉取最新的“大脑”与“肌肉”。

## When to Use
- 在 `link.json` 中 `link_type` 为 `copy` 时。
- 想要获取母库最新发布的 Skill 或 Pattern 时。
- 想要重置受损的本地技能库时。

## Implementation Workflow (Step-by-Step)

### 1. Source Identification
- [ ] **读取路径**：AI 必须首先读取 `.gemini/link.json` 中的 `foundry_root`。
- [ ] **路径验证**：验证母库路径是否物理存在。

### 2. Physical Sync (Incremental)
AI 必须执行以下物理拷贝动作，将资产从母库推向子库。

- [ ] **同步技能库**：
  ```bash
  xcopy "{{FOUNDRY_ROOT}}\.gemini\skills" .gemini\skills /E /Y /D
  ```
- [ ] **同步图纸库**：
  ```bash
  xcopy "{{FOUNDRY_ROOT}}\patterns" patterns /E /Y /D
  ```
  *注：`/D` 参数确保仅拷贝较新或缺失的文件，保护已存在的本地逻辑。*

### 3. Verification
- [ ] **审计记录**：在 `.gemini/ops_changelog.md` 中记录本次同步时间与来源。
- [ ] **状态报告**：汇报新增或更新的技能清单。

## Red Flags
- 同步过程中未指定 `/D` 参数，导致本地已有的配置被无差别覆盖。
- 在没有 `link.json` 的情况下盲目同步。

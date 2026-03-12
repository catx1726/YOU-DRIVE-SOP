---
name: meta-distiller
description: Use when distilling logic from business code to Mother-Base with Staging approval and Skill-Pattern linkage.
---

# Meta Distiller (Logic & Knowledge Refinement)

## Overview
本技能是 SOP 2.0 体系的“提纯专家”。它负责将业务代码中的碎片逻辑转化为标准的物理图纸（Pattern）与智力资产（Skill），并通过“暂存区（Staging）”机制确保母库的受控演进。

## When to Use
- 在任务归档前执行“资产提纯”。
- 将子库中的通用模块反哺给母库。
- 建立“方法论（Skill）”与“实现（Pattern）”的闭环。

## Core Pattern: Controlled Evolution
1. **Staging Approval**: 所有提纯资产优先写入子库 `.gemini/distill_stage/`，禁止直接跨库写入母库。
2. **Skill-Pattern Linkage**: 
   - **Skill (common-xxx.md)**: 定义“为什么用”、“何时用”，并包含指向 Pattern 的 Markdown 链接。
   - **Pattern (patterns/xxx/)**: 提供 index 三件套（代码、测试、说明）。
3. **Automatic Distillation**: 依据 `env.md` 的词库自动执行正则参数化（`{{VAR}}`）。

## Implementation Workflow

### 1. Identify & Extract
- 识别高价值逻辑，提取 IPO (Input-Process-Output) 模型。
- 执行参数化处理，移除所有业务特有词汇。

### 2. Staging Generation
- 在子库创建 `.gemini/distill_stage/` 目录。
- **Generate Pattern**: 在 `distill_stage/patterns/<name>/` 下生成 `index.ts`, `index.test.ts`, `README.md`。
- **Generate Skill**: 在 `distill_stage/skills/` 下生成 `common-<name>.md`。
  - *Reference Pattern*: 在 Skill 文档中显式声明：`**Implementation**: [Source Code]({{FOUNDRY_ROOT}}\patterns\<name>\index.ts)`。

### 3. Local Verification
- 在子库尝试运行 `vitest` 验证 Staging 中的逻辑。

### 4. Integration (The Contribution Loop)
- 在 `/opsx:archive` 触发时，扫描 `distill_stage/`。
- 若用户确认合并，执行跨库 `mv` 至母库根目录对应的 `patterns/` 和 `skills/`（扁平化路径）。

## Common Mistakes
- **逻辑重复**：未检查母库是否已有同类 Pattern。
- **硬编码路径**：在 Skill 文档中使用相对于当前子库的相对路径。*修正：必须使用相对于母库根目录的变量或绝对路径。*
- **忽略 Skill 提纯**：只收割代码不总结经验。

## Red Flags
- 提纯资产中保留了未经参数化的业务关键词。
- Skill 文档缺少 `Use when...` 触发描述。
- 暂存区缺少 Vitest 测试用例。

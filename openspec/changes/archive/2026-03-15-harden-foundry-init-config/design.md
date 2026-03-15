## Context

目前 `foundry-initializing` 虽然能创建目录，但在生成 `config_foundry.yaml` 时缺乏实质性内容。这使得子库在执行 `workshop-initializing` 时同步到的配置是“空壳”。

## Goals / Non-Goals

**Goals:**
- 确保母库初始化产出的 `config_foundry.yaml` 包含 SOP 2.0 全量元数据。
- 将“任务 0：规约自检”的任务模板固化到初始配置中。

**Non-Goals:**
- 修改 `openspec` 内部的配置解析算法。

## Decisions

- **硬编码最佳实践模板**：在技能中直接定义一个高质量的配置模板，在初始化时物理写入。
- **强制覆盖校验**：初始化时若发现已存在但不完整的配置，应提醒用户并提供覆盖选项。

## Risks / Trade-offs

- **[Risk]** 覆盖用户自定义配置 -> **[Mitigation]** 仅在 `foundry-initializing` 阶段执行，且增加“若已存在则增量补丁”的逻辑。

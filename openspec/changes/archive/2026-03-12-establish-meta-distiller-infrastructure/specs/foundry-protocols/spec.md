## MODIFIED Requirements

### Requirement: 逻辑提纯协议 (logic_schema)
逻辑提纯 SHALL 引入暂存审核（Staging）与联动引用标准。
- **暂存机制**：子库提纯的资产必须首先存入 `.gemini/distill_stage/`，禁止直接写入母库。
- **联动标准**：
    - **Skill** 负责“触发”与“指路”，必须包含指向对应 Pattern 的物理路径链接。
    - **Pattern** 负责“实现”与“验证”，必须包含标准的 index 三件套。
- **参数化增强**：提取过程必须根据子库 `env.md` 定义的词库执行全量去业务化。

#### Scenario: 跨库资产反哺流
- **WHEN** AI 执行 `meta-distiller`。
- **THEN** 系统在子库 `.gemini/distill_stage/` 生成一份去业务化的逻辑副本及对应的 `common-` 技能初稿，并等待用户审批。

### Requirement: 归档门禁 (openspec-changes-archive)
归档流程 SHALL 包含暂存资产的合并决策。
- 在移动 Change 文件夹至 archive 前，必须扫描 `.gemini/distill_stage/`。
- **用户确认**：若发现暂存资产，必须询问用户是否执行“并入母库”操作。

#### Scenario: 任务结束即资产入库
- **WHEN** 用户执行 `/opsx:archive`。
- **THEN** AI 提示：『检测到暂存资产，是否将其并入母库 patterns/ 和 skills/？』，并在用户确认后执行物理迁移与验证。

## MODIFIED Requirements

### Requirement: 逻辑提纯协议 (logic_schema)
逻辑提纯 SHALL 执行物理目录标准化和参数化。
- **存储标准**：存入 `patterns/` 的每个资产必须包含 `index.ts`, `index.test.ts`, `README.md`。
- **参数化**：所有项目特定词汇必须替换为 `{{VAR_NAME}}`。
- **能力化**：每个 Pattern 必须配套一份存入母库 `skills/` 的 `common-<name>.md` 指令文件。

#### Scenario: 工业级资产沉淀
- **WHEN** AI 完成逻辑提取。
- **THEN** 系统自动构建 `patterns/` 目录结构，并利用 `writing-skills` 将该逻辑转化为一份通用 Skill，确保未来 AI 可直接通过名称激活该能力。

### Requirement: 归档门禁 (openspec-changes-archive)
归档流程 SHALL 强制集成资产收割检查。
- 在 `mv` 至 archive 目录前，必须调用 `asset-harvesting` 技能。
- 必须在归档摘要中显式列出：『收割的 Pattern 路径』与『生成的 Skill 名称』。

#### Scenario: 闭环归档
- **WHEN** 用户执行 `/opsx:archive`。
- **THEN** AI 提示：『正在检测可收割资产...』，并在提纯完成后才正式移动任务文件夹。

## MODIFIED Requirements

### Requirement: 环境指纹识别 (workshop-initializing)
子库对齐 SHALL 包含链路持久化与规约同步。
- **物理链路**：必须在子库创建 `.gemini/link.json` 记录母库绝对路径。
- **规约同步**：必须将母库的 `openspec/schemas/` 核心协议注入子库本地，确保 OpenSpec 工具能正确执行规约检查。

#### Scenario: 跨库规约可见性
- **WHEN** 子库执行对齐流程。
- **THEN** 系统自动生成 `link.json`，并同步 `env_schema.md`, `logic_schema.md` 等协议至子库 `openspec/schemas/foundry/` 目录。

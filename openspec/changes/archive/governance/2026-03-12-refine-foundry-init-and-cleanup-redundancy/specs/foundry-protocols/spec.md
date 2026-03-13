## MODIFIED Requirements

### Requirement: 母库初始化 (foundry-initializing)
母库初始化 SHALL 具备全量规约继承能力并保持物理极简。
- **模板注入**：初始化不再创建空文件，必须同步注入框架内置的 `Global Standard` 与 `Schemas` 模板内容。
- **物理去冗余**：技能目录必须保持扁平，禁止在 `skills/` 下创建 `meta/`、`common/` 等嵌套物理目录。
- **成功反馈**：初始化完成后，必须提供包含工具链状态与规约摘要的总结报告。

#### Scenario: 即插即用的母库建立
- **WHEN** 用户执行 `foundry-initializing`。
- **THEN** 系统在创建目录的同时，自动填充打磨好的核心协议文件，使用户无需手动配置即可开始资产沉淀。

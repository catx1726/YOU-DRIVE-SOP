## MODIFIED Requirements

### Requirement: 逻辑提纯协议 (logic_schema)
逻辑提纯协议 SHALL 强制要求在收割代码时移除所有业务特定变量，并执行原子化封装。
- 提取逻辑必须符合“输入-处理-输出（IPO）”契约。
- 必须使用 `{{VAR_NAME}}` 格式执行参数化去业务化。
- 禁止提取耦合具体业务 UI（如特定样式类、项目图标）的代码。

#### Scenario: 资产去业务化收割
- **WHEN** AI 从子库提取一个去业务化的业务处理模块（Decoupled Business Module）。
- **THEN** 系统检测逻辑中是否含有项目私有变量，并依据 `logic_schema` 强制将其替换为参数占位符，最终存入母库 `patterns/`。

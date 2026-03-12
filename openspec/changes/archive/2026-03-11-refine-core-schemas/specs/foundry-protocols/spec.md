## ADDED Requirements

### Requirement: 环境协议 (env_schema)
环境协议 SHALL 定义一套标准的指纹识别规则，以评估子库（Workshop）与母库（Foundry）的技术栈对齐程度。
- 必须包含 Node 20.x, npm 10.x 强制标准检查。
- 必须支持禁止读取清单（Deny-List），防止敏感配置被收割。
- 必须包含关键依赖（如 Vue, React, Vite）的指纹识别。

#### Scenario: 环境指纹识别
- **WHEN** 子库执行 `workshop-initializing`。
- **THEN** 系统根据 `env_schema` 扫描 `package.json`，并在子库生成 `openspec/specs/env.md`，明确列出与 Node 20 标准的偏差。

### Requirement: 逻辑提纯协议 (logic_schema)
逻辑提纯协议 SHALL 强制要求在收割代码时移除所有业务特定变量，并执行原子化封装。
- 提取逻辑必须符合“输入-处理-输出（IPO）”契约。
- 必须使用 `{{VAR_NAME}}` 格式执行参数化去业务化。
- 禁止提取耦合具体业务 UI（如特定样式类、项目图标）的代码。

#### Scenario: 资产去业务化收割
- **WHEN** AI 从子库提取一个 Canvas 渲染逻辑。
- **THEN** 系统检测逻辑中是否含有项目私有变量，并依据 `logic_schema` 强制将其替换为参数占位符，最终存入母库 `patterns/`。

### Requirement: 架构决策协议 (decision_schema)
架构决策协议 SHALL 规范 ADR 的编写格式，确保所有演进记录均包含完整的背景和后果评估。
- ADR 必须包含 Status (Proposed, Accepted, etc.)。
- 必须包含 Consequences 字段。
- 必须支持关联子库（Related Project）字段。

#### Scenario: 记录跨库技术妥协
- **WHEN** 在子库中因为旧版 Webpack 限制而选择了替代方案。
- **THEN** 系统依据 `decision_schema` 在子库生成一份 ADR，详细记录该妥协的背景及其对母库资产同步的影响。

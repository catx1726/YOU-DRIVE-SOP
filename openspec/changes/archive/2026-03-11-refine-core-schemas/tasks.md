# Tasks

## 1. 建立环境协议 (env_schema)
- [x] 在 `openspec/schemas/env_schema.md` 生成模板。
- [x] 定义 Node 20 / npm 10 强制基准。
- [x] 预置常见项目（Vue 2, Node 20）的依赖指纹清单。

## 2. 建立逻辑提纯协议 (logic_schema)
- [x] 在 `openspec/schemas/logic_schema.md` 生成模板。
- [x] 定义逻辑提取的 IPO (Input-Process-Output) 契约结构。
- [x] 固化 `{{VAR_NAME}}` 参数化去业务化规则。
- [x] 增加 Vitest 测试规格的强制引用。

## 3. 建立决策协议 (decision_schema)
- [x] 在 `openspec/schemas/decision_schema.md` 生成模板。
- [x] 定义 ADR 的标准分段（Status, Context, Decision, Consequences）。
- [x] 预置 `Proposed`, `Accepted`, `Superseded` 的状态枚举说明。

## 4. 全局验证与集成
- [x] 模拟 `workshop-initializing` 调用这些 Schema。
- [x] 确保母库的 `global_standard.md` 与这些 Schema 在逻辑上闭环。

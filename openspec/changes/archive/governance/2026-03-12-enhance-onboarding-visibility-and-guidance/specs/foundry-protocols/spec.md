## MODIFIED Requirements

### Requirement: 环境指纹识别 (workshop-initializing)
子库对齐 SHALL 提供高可见性的交互引导。
- **看板注入**：初始化生成的 `GEMINI.md` 必须包含「🚀 快速操作看板」，涵盖核心治理（OpenSpec）与执行（Superpowers）指令。
- **意图引导**：初始化流程末尾必须包含一个交互式询问点，根据用户选择（如：逆向或开发）自动进入下一步逻辑。

#### Scenario: 看板辅助驱动
- **WHEN** 用户在子库启动 Gemini CLI。
- **THEN** AI 自动读取 `GEMINI.md` 看板，并在欢迎语中列出：`/opsx:propose`, `legacy-extractor`, `meta-rollback` 等常用指令，使驾驶员无需翻阅文档即可开始操作。

#### Scenario: 初始化的“新手村”引导
- **WHEN** `workshop-initializing` 执行完毕。
- **THEN** AI 暂停并提问：『您现在是想扫描旧项目（输入 A）还是开发新功能（输入 B）？』，并根据响应展示第一条指令的操作细节。

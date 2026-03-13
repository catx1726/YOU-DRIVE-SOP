# OpenSpec 功能挖掘简报 (Foundry Upstream Audit)

## 1. 核心治理逻辑增强
- **状态机依赖管理**：OpenSpec 原生支持产物间的 `unlocks` 逻辑。
- **[集成建议]**：将 `meta-step-runner` 升级，支持基于依赖的任务拓扑排序，而非线性排序。

## 2. 隐藏指令挖掘
- **`/opsx:sync`**：用于主规格与 Delta Spec 之间的强制同步。
- **`/opsx:verify`**：用于验证当前 Change 是否符合 Specs 定义。
- **`/opsx:onboard`**：用于将现有库导入 OpenSpec 管理。
- **[集成建议]**：在 `YOU-DRIVE-SOP` 手册中映射这些指令，将 `onboard` 与我们的初始化逻辑深度缝合。

## 3. 工业级路径标准
- **Path Sentinel**：上游严禁在规约中使用硬编码斜杠。
- **[集成建议]**：在 `logic_schema.md` 中增加“跨平台路径校验”门禁，强制收割资产使用动态路径处理。

## 4. 协作礼仪
- **版权声明**：需在 `README.md` 明确引用 `git@github.com:Fission-AI/OpenSpec.git` 并致敬。

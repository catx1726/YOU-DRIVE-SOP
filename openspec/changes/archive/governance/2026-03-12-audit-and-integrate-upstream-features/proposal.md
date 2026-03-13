## Why

YOU-DRIVE-SOP 深度依赖于 OpenSpec 和 Superpowers。目前我们仅使用了它们的基础功能，可能忽略了其原生的、更高级的治理逻辑与插件机制。为了实现真正在巨人肩膀上的演进，我们需要通读上游源码与文档，挖掘隐藏功能，并将其标准化地融入我们的工作流。同时，在 README 中补齐版权致敬，确保合规性。

## What Changes

- **深度审计上游库**：分步扫描 `tools/` 下的三个源库（OpenSpec, gemini-superpowers, superpowers）。
- **功能融合与提纯**：提取上游的高级指令、验证钩子及压力测试用例，并反哺至母库。
- **更新开源门面**：在 README 中显式声明上游依赖并致敬原作者。
- **流程优化**：根据上游原生逻辑，调整我们的 `meta-` 级元技能。

## Capabilities

### New Capabilities
- `upstream-bridge`: 建立一个用于持续同步上游更新的参考规约。

### Modified Capabilities
- `foundry-protocols`: 根据上游发现调整治理与执行标准。

## Impact
- 提高了 YOU-DRIVE-SOP 与上游工具的兼容性与协作深度。
- 增强了框架的功能浓度。

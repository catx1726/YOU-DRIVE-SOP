## Why
当前的物理链路建立逻辑存在“黑盒”现象：当 `gemini skills link` 由于权限或环境原因无法建立 Junction 时，会静默回退为全量复制。这导致子库失去了母库规约的实时同步能力，且用户对此并不知情。

## What Changes
- **策略显式化**：修改 `workshop-initializing` 技能，确立“链接优先（Junction），复制回退（Copy）”的顺序逻辑。
- **状态报告**：要求 AI 在链接动作后明确报告当前的物理类型（Linked vs Copied）。
- **风险告知**：若发生回退复制，AI 必须警告用户：『当前为复制模式，母库更新将无法自动同步至本库。』

## Capabilities
- `hybrid-link-handler`: 具备自动识别并处理链接与复制回退的逻辑能力。

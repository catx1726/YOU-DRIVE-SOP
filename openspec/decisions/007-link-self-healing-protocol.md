# ADR-007: 链接自愈协议 (Link Self-Healing Protocol)

## Status
Accepted

## Context
在 SOP 2.0 的长期演进中，母库的物理路径可能由于项目迁移、存储优化或系统环境变化而发生变动。由于子库通常使用 Windows Junction 或 Symlink 挂载母库技能，一旦源路径变动，所有本地链接将失效（显示为损坏的文件夹或 EPERM 错误）。目前缺乏一种标准化的、幂等的修复机制，导致手动维护成本高且易出错。

## Decision
1. **定义自愈逻辑**：在 `workshop-initializing` 技能中注入专门的自愈章节。
2. **属性化识别**：利用 Windows 的 `ReparsePoint` 属性精准识别链接目录，防止误操作本地真实文件。
3. **幂等重建**：修复过程遵循“清理 -> 重新扫描 -> 重新映射”的闭环，确保结果的唯一性。
4. **语义化触发**：定义 "Refresh skills reference from template" 等标准触发指令，使 AI 能够主动建议并执行修复。

## Consequences
- **好处**：实现了跨库链路的“零成本”维护；确保了子库始终能同步母库的最强智力资产；提高了体系的健壮性。
- **约束**：要求 AI 具备识别文件系统底层属性的能力（ReparsePoint）；修复动作需保证对非链接目录（如 `openspec-bridge`）的绝对安全。

## Related Sub-Project
N/A (SOP 2.0 Governance Refinement)

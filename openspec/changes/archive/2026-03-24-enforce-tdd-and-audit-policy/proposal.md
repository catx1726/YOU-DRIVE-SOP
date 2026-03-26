## Why
为了实现 SOP 2.0 的“物理熔断”目标，必须从当前的“Skill 规约提示”转向“Policy Engine 强制拦截”。目前的 TDD 和操作留痕机制仅能触发警告，若 AI 引擎执行惯性导致跳过，系统无法自我修复。

## What Changes
- **强化审计锁 (Audit Lock)**: 完善 `meta-safe-executor` 逻辑，要求任何物理变更必须校验日志。
- **强化 TDD 门控**: 升级 `verification-before-completion` 的前置守卫，确保自动化测试必须通过。

## Capabilities
- `physical-audit-gate`: 确保写操作与审计日志物理强关联。
- `tdd-preflight-gate`: 确保 Verify 环节包含自动化测试物理熔断。

## Impact
- 提升工程纪律的物理强制性，消除“AI 赶时间跳过规约”的技术债。

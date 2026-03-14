# ADR 026: 归档分流强制化与资产三件套标准

## 状态 (Status)
已通过 (Accepted)

## 上下文 (Context)
在授权窗口内的 SOP 2.0 压力测试中发现，虽然规约要求治理类资产分流存储，但 OpenSpec CLI 默认仅归档至 `archive/` 根目录，且 AI 在执行时容易忽略后续的手动物理搬迁动作。同时，资产入库时缺乏对“测试与文档”齐备性的硬性校验。

## 决策 (Decision)
1.  **归档技能加固**：修改 `openspec-changes-archive` 技能，将“手动执行治理分流指令”提升为 **Mandatory (强制)** 步骤，并明确了 Windows 环境下的 `Remove-Item` 清理规范。
2.  **资产完整性门禁**：在 `foundry-protocols` 中新增 `Source-to-Pattern Integrity` 规约，确立“三件套”（代码、测试、README）为资产入库的唯一准入条件。
3.  **物理闭环校验**：强制 AI 在归档前检查 Staging 区的物理结构，缺失任何一项均视为违规。

## 后果 (Consequences)
- **正面**：消除了母库资产分布的随机性；保证了反哺资产的 100% 生产级可用性。
- **负面**：归档操作增加了约 2-3 个物理指令的执行成本，但换取了极高的架构整洁度。

---
*Created on 2026-03-14 by YOU-DRIVE-SOP Engine (Autonomous Mode).*

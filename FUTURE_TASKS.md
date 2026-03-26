# 通用战略议题池 (General Backlog)

本文档记录了与 13 步生产协议无直接绑定关系的、业务或技术层面的待探索议题。

---

## 1. 物理层：Policy Engine 熔断机制 (Tech Spike)
- **目标**: 实现对 `rm`, `mv`, `Clear-Content` 等危险命令的物理拦截。
- **状态**: 待调研

## 2. 状态融合层：双环状态模型 (Architecture Design)
- **目标**: 将 OpenSpec 任务状态与 Superpowers 的执行 TODO 列表自动同步。
- **状态**: 待设计

## 3. 协作层：多智能体并发 (Multi-Agent Delegation)
- **目标**: 实现 Agent 任务拆解、多 Worker 并发、冲突合并。
- **状态**: 待调研

---

## 4. 协议自动化增强 (Protocol Automation Hardening)

### 4.1 节点 03: 分支命名物理熔断
- **目标**: 通过 Git Hook 或 Policy 拦截非 `issue-N` 命名的分支上的写操作。

### 4.2 节点 07: 审计留痕 CI 强校验
- **目标**: 编写 GitHub Actions，检查 PR 提交中是否包含 `.gemini/ops_changelog.md` 的物理行更新。

### 4.3 节点 10: 提纯动作与归档绑定
- **目标**: 优化 `openspec-archive` 技能，使其在检测到业务代码变更而无 Staging 产物时，自动触发 `meta-distiller`。


# SOP 2.0 物理审计库 (Operations Audit Library)

## 1. 定位说明
本目录专门存放执行层（Operations）的审计日志痕迹，包括 ops_changelog.md 和各任务的物理操作快照。

## 2. 存储结构
- **archive/**: 存放已归档任务的操作痕迹，路径与 governance/ 保持 1:1 映射。

## 3. 治理分流原则 (Separation of Concerns)
- **Governance 档案**: 存放『为什么做』和『做了什么』（Proposal, Design, Specs）。
- **Operations 档案**: 存放『具体是怎么操作的』（Changelog, Undo Commands）。

---
*YOU-DRIVE-SOP Core Infrastructure*

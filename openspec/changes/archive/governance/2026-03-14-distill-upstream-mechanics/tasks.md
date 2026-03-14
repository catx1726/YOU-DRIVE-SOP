## 1. 源码深度扫描 (Source Deep-Dive)

- [ ] 1.1 分步读取 `tools/OpenSpec/src/` 目录下的 `cli.ts` (或主要入口)。
- [ ] [ ] 1.2 读取 `src/engine/` (或等效核心逻辑目录)，识别工件依赖拓扑的计算方式。
- [ ] 1.3 **Validation**: AI 能够物理输出 OpenSpec 的内部“工件依赖状态机”图示。

## 2. 核心逻辑解构 (Mechanics Deconstruction)

- [ ] 2.1 识别 OpenSpec 如何处理 `delta operations` (ADDED/MODIFIED/REMOVED)。
- [ ] 2.2 识别归档动作对 Git 分枝的真实物理要求。
- [ ] 2.3 **Validation**: 输出一份包含至少 5 个“源码级发现”的技术草案。

## 3. 规约固化 (Hardening)

- [ ] 3.1 创建 `openspec/specs/upstream-lineage/openspec-core.md`。
- [ ] 3.2 将解构心得转化为符合 SOP 2.0 标准的 Requirements。
- [ ] 3.3 执行 `:archive` 物理归档。
- [ ] 3.4 **Integrity Check**: Process Compliance Verification (Logs, Language, PR)。

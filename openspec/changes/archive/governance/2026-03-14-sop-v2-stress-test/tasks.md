## 1. 逻辑提纯演练 (Distillation Drill)

- [ ] 1.1 编写一个模拟业务逻辑（如：`array-uniqueness-util.ts`）。
- [ ] 1.2 激活 `meta-distiller` 将其提纯至 Staging 阶段。
- [ ] 1.3 验证“三件套”标准（代码、测试、README）是否物理生成。
- [ ] 1.4 **Validation**: 运行配套测试并观察 AI 对“参数化”的理解。

## 2. 规约对齐压力测试 (Spec Alignment Stress)

- [ ] 2.1 模拟开启一个全新的会话环境。
- [ ] 2.2 触发 `GEMINI.md` 的 `[CRITICAL-BOOT-SEQUENCE]`。
- [ ] 2.3 验证 AI 是否能自主定位到 `openspec-core.md` 并准确总结卡恩算法。
- [ ] 2.4 **Validation**: AI 的状态汇报是否涵盖了所有 4 个层级的治理架构。

## 3. 自动化归档与分流验证 (Archive & Partitioning)

- [ ] 3.1 对本压力测试任务执行 `/opsx:archive`。
- [ ] 3.2 验证治理单是否进入 `archive/governance/sop-v2-stress-test/`。
- [ ] 3.3 验证审计日志 `.gemini/ops_changelog.md` 是否被清空并迁移。
- [ ] 3.4 **Validation**: 物理检查分流路径的 100% 准确性。

## 4. 故障自我修复 (Self-Repair)

- [ ] 4.1 记录所有在上述过程中遇到的“物理报错”（如 EPERM, IO 冲突）。
- [ ] 4.2 根据报错原因，自主修改 `foundry-protocols/spec.md` 或相关 Skill。

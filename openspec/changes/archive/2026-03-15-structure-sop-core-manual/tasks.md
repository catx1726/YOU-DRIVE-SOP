## 1. 规约与环境自检 (Mandatory Setup)

- [x] 1.1 确认当前分支为 `issue-028-structure-core-manual`（禁止在 main 直接操作）
- [x] 1.2 确认已在 `.gemini/ops_changelog.md` 记录本次操作表格
- [x] 1.3 执行 `activate_skill verification-before-completion` 预载验证逻辑

## 2. 核心手册重构 (SOP Core Manual)

- [x] 2.1 在 `SOP_CORE_MANUAL.md` 第 0 章增加 SOP 2.0 三层架构图 (Foundry-Change-Asset)。
- [x] 2.2 更新手册中的核心定义，确保与 `openspec-core.md` 中的术语一致。
- [x] 2.3 **Validation**: 读取渲染后的 `SOP_CORE_MANUAL.md` 确认图表清晰度。

## 3. 入门指南重构 (Getting Started)

- [x] 3.1 重写 `GETTING_STARTED.md`，拆分为 "Foundry Manager" 和 "Asset Harvester" 两条路径。
- [x] 3.2 增加 Windows 下的 Symlink 故障排除指南。
- [x] 3.3 **Validation**: 模拟新用户视角，验证两个角色的操作闭环。

## 4. 过程合规性校验 (Compliance Verification)

- [x] 4.1 确认所有写操作均有审计记录
- [x] 4.2 确认 PR 描述已准备就绪

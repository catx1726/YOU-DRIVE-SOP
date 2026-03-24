## 1. 规约与环境自检 (Mandatory Setup)

- [x] 1.1 确认当前处于 Issue 分支，避免在 `main` 直接操作
- [x] 1.2 初始化审计日志 `.gemini/ops_changelog.md` 记录本次重构起点
- [x] 1.3 验证 `meta-safe-executor` 处于就绪状态

## 2. 架构真值源收口 (Architecture SSOT)

- [x] 2.1 更新 `ARCHITECTURE.md`：引入“骨架-肌肉”二元模型定义与引擎分层说明
- [x] 2.2 更新 `ARCHITECTURE.md`：绘制 `meta-distiller` 提纯微观流程图
- [x] 2.3 更新 `ARCHITECTURE.md`：绘制 `OpenSpec` 状态机微观流程图
- [x] 2.4 验证：Mermaid 语法正确且图表逻辑与实际规约对齐

## 3. 文档去重与内容迁移 (De-duplication & Migration)

- [x] 3.1 迁移：将 `SOP_CORE_MANUAL.md` 中的架构定义迁移至 `ARCHITECTURE.md`，并在原处保留链接
- [x] 3.2 迁移：将 `GEMINI.md` 中的详细角色定义迁移至 `ARCHITECTURE.md`
- [x] 3.3 迁移：删除 `AGENTS.md`，并将其核心入口逻辑合并至 `GEMINI.md` 的 [CRITICAL-BOOT-SEQUENCE]
- [x] 3.4 验证：所有被移除内容的旧路径已指向新 SSOT，且无死链

## 4. 递归模式指南 (Recursive Mode Guide)

- [x] 4.1 更新 `GETTING_STARTED.md`：新增 "Recursive Mode (Self-Evolution)" 章节
- [x] 4.2 编写：在指南中提供 `FOUNDRY_PATH` 的本地配置示例与操作注意事项
- [x] 4.3 验证：指南内容能够指导开发者在不破坏母库的情况下完成自演进提案

## 5. 合规性校验与收尾 (Process Compliance Verification)

- [x] 5.1 执行全局链接自检：确保 `ARCHITECTURE.md` 为核心引用的唯一中心
- [x] 5.2 更新 `.gemini/ops_changelog.md` 记录所有物理文件变动轨迹
- [x] 5.3 检查语言一致性：确保所有新文档遵循“专业、直接、去填充”的准则
- [x] 5.4 准备归档：运行 `openspec status` 确认所有 artifact 已完成，准备执行 `/opsx:apply`

## 1. 强化母库种子能力 (Foundry Bootstrapping)

- [x] 1.1 修改 `foundry-initializing` 技能，增加对 `openspec/specs/vcs-lifecycle-automation` 等模板的自动生成逻辑。
- [x] 1.2 在 `foundry-initializing` 中增加对 `global_standard.md` 的内容对齐校验。
- [x] 1.3 **验证**：在测试目录下运行 `foundry-initializing` 并确认物理文件完整。

## 2. 实现全量规约同步 (Workshop Full Alignment)

- [x] 2.1 修改 `workshop-initializing` 技能，实现母库 `openspec/specs` 目录的递归物理拷贝。
- [x] 2.2 在 `workshop-initializing` 末尾增加物理审计步骤，输出已同步的规约 Markdown 表格。
- [x] 2.3 **验证**：在新建子库中运行初始化，检查 `openspec/specs` 是否 100% 同步。

## 3. 增强引导感知与流程防呆

- [x] 3.1 修改子库 `GEMINI.md` 生成模板，注入动态状态查询指令（如“目前初始化状态如何？”）。
- [x] 3.2 更新 `using-superpowers` 技能，在会话开始时检测初始化物理标志位。
- [x] 3.3 **验证**：在新会话中观察 AI 是否能根据 `link.json` 的缺失主动提示初始化。

## 4. 流程规约校验 (Compliance)

- [x] 4.1 更新 `.gemini/ops_changelog.md` 记录本次修复的完整闭环。
- [x] 4.2 **验证**：确保所有的 `replace` 动作均通过 `meta-safe-executor` 执行。
- [x] 4.3 过程合规性校验（日志、中文、PR）。

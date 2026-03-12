# YOU-DRIVE-SOP 快速入门指南

欢迎使用 **YOU-DRIVE-SOP** 框架。本指南将带您完成首个 Foundry (母库) 与 Workshop (工作间) 的搭建。

## 第一步：搭建 Foundry (母库)

**Foundry** 是您的中央知识库，存储着所有项目共享的技能（Skills）与代码模式（Patterns）。

1. **克隆模板**：
   ```bash
   git clone https://github.com/your-repo/YOU-DRIVE-SOP.git my-foundry
   cd my-foundry
   ```

2. **初始化母库**：
   ```bash
   activate_skill foundry-initializing
   ```
   *此操作将建立目录结构并注入全局标准。*

## 第二步：设置 Workshop (工作间)

**Workshop** 是您编写实际业务代码的项目。它通过“链接”到 Foundry 来获取智力支持。

1. **进入您的项目目录**：
   ```bash
   cd /path/to/your/project
   ```

2. **建立技能链接**：
   ```bash
   gemini skills link /absolute/path/to/my-foundry/.gemini/skills --scope workspace --consent
   ```

3. **执行对齐初始化**：
   ```bash
   activate_skill workshop-initializing
   ```
   *此操作将识别您的技术栈，并自动生成 GEMINI.md 以引用母库宪法。*

## 第三步：首个开发自演进循环

一旦链接完成，请在每一项任务中遵循以下闭环逻辑：

1. **发起提案**：
   ```bash
   /opsx:propose my-new-feature
   ```
   *AI 将根据母库的图纸分析需求并生成设计。*

2. **纪律化实施**：
   ```bash
   /opsx:apply
   ```
   *坚持 TDD 标准，实现逻辑与 UI 的分离。*

3. **资产提纯 (核心步)**：
   在归档前，AI 会提示您提炼通用逻辑。
   ```bash
   activate_skill meta-distiller
   ```

4. **归档与反哺**：
   ```bash
   /opsx:archive
   ```
   *任务圆满结束，您的母库也因此变得更强大。*

---

## 🛡️ 最佳实践

- **路径动态化**：永远不要在 Skill 中硬编码路径，利用框架的自动探测能力。
- **暂存审批**：利用 Staging 区域 (`.gemini/distill_stage/`) 在资产正式入库前进行最后的代码审查。
- **安全第一**：确保项目处于 Git 管理下，以激活自动备份与回滚功能。

*祝您驱动愉快！*

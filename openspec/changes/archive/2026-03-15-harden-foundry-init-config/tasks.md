## 1. 规约与环境自检 (Mandatory Setup)

- [x] 1.1 确认当前分支为 `issue-029-harden-foundry-init`
- [x] 1.2 确认 `.gemini/ops_changelog.md` 审计表格已更新
- [x] 1.3 执行 `activate_skill verification-before-completion` 预载验证逻辑

## 2. 技能加固 (Skill Hardening)

- [x] 2.1 修改 `foundry-initializing` 技能，在 Step 1 中定义一个全量的 `config_foundry.yaml` 模板字符串。
- [x] 2.2 在 `foundry-initializing` 逻辑中增加物理写指令，确保 `openspec/config_foundry.yaml` 被正确创建。
- [x] 2.3 **Validation**: 在空目录下测试 `foundry-initializing`，检查生成的 yaml 是否包含 templates 段。

## 3. 过程合规性校验 (Compliance Verification)

- [x] 3.1 确认所有物理写操作均有审计日志
- [x] 3.2 准备 PR 描述摘要

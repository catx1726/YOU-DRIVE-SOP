## 1. 规约与环境自检 (Mandatory Setup)
- [ ] 1.1 确认当前分支为 `issue-037-git-isolation`
- [ ] 1.2 确认审计日志已记录
- [ ] 1.3 预载验证逻辑

## 2. 技能加固 (Isolation Hardening)
- [ ] 2.1 修改 `workshop-initializing` 技能，在 Step 1 之前插入 **「Git 物理隔离预检」**。
- [ ] 2.2 在 `workshop-initializing` 中增加物理写入 `.gitignore` 的自动化逻辑。
- [ ] 2.3 **Validation**: 在带 Git 的空目录下运行初始化，检查是否自动生成了正确的忽略规则。

## 3. 规约与文档同步
- [ ] 3.1 更新 `GETTING_STARTED.md`，在子库 setup 章节增加关于 Git 隔离的风险提示。
- [ ] 3.2 更新 `link-self-healing-protocol` 规约，强调隔离是自愈的前提。

## 4. 过程合规性校验
- [ ] 4.1 审计归档

## 1. 启动清单加固 (Critical Boot Sequence Hardening)
- [ ] 1.1 修改 `GEMINI.md`：引入 [三层物理读取链] 定义
- [ ] 1.2 修改 `GEMINI.md`：将核心配置文件探测逻辑硬编码进 [CRITICAL-BOOT-SEQUENCE]

## 2. 治理资产对齐 (Asset Synchronization)
- [ ] 2.1 审核 `openspec/config*.yaml` 是否完整包含测试与熔断配置
- [ ] 2.2 确认所有 `.gemini/commands/*.toml` 是否均已满足自动化联动逻辑

## 3. 合规性校验 (Compliance)
- [ ] 3.1 运行 `workshop-initializing` 并验证文件链接是否指向正确
- [ ] 3.2 运行 `/opsx:archive` 进行最终物理结转

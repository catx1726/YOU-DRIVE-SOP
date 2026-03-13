## 1. 母库初始化加固 (Foundry Init Hardening)

- [ ] 1.1 修改 `.gemini/skills/foundry-initializing/SKILL.md`，增加 `Step 0: Upstream Deep-Dive`。
- [ ] 1.2 在该步骤中定义 AI 必须读取 `tools/OpenSpec/schemas/` 和 `tools/superpowers/skills/` 的物理动作。
- [ ] 1.3 **Validation**: 执行 `activate_skill foundry-initializing` 并请求 AI 汇报其对上游 Schemas 的理解。

## 2. 子库初始化加固 (Workshop Init Hardening)

- [ ] 2.1 修改 `.gemini/skills/workshop-initializing/SKILL.md`，增加 `Step 5: Foundry Manual Alignment`。
- [ ] 2.2 定义 AI 必须执行 `read_file {{FOUNDRY_ROOT}}/SOP_CORE_MANUAL.md`。
- [ ] 2.3 **Validation**: 模拟子库初始化环境，验证 AI 是否主动展示手册中的核心规约。

## 3. 规约与合规 (Governance & Compliance)

- [ ] 3.1 更新 `SOP_CORE_MANUAL.md`，显式标注“智力继承”机制。
- [ ] 3.2 执行 `:archive` 物理归档。
- [ ] 3.3 **Integrity Check**: Process Compliance Verification (Logs, Language, PR)。

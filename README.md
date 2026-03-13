# YOU-DRIVE-SOP

> **"AI 驱动逻辑，你驱动规约。"**

YOU-DRIVE-SOP 是一个开源框架，旨在帮助开发者构建、精炼并演进属于自己的 AI 驱动标准作业程序（SOP）。它将您的开发过程转化为一个自主演进的实验室，使每一项任务都能为不断增长的可重用智力库做出贡献。

---

## 🚀 核心哲学

在 YOU-DRIVE-SOP 的世界里，AI 是引擎，而你始终是驾驶员。

- **自主沉淀**：您构建的每个特性都是全球智力库的潜在候选资产。
- **自演进**：框架会从您的更正和架构决策中持续学习。
- **Foundry & Workshop**：中央 **Foundry (母库)** 存储您的全局技能与模式，而本地 **Workshop (工作间)** 则对齐这些标准以确保高质量产出。

## 🛠️ 工具链手册

### 1. OpenSpec (opsx) - 治理与生命周期管理
OpenSpec 是本项目底层采用的变更管理标准。它负责管理任务的“状态流转”。
- `/opsx:propose <name>`：发起新提案。AI 将生成 Proposal (为什么做) 与 Design (怎么做)。
- `/opsx:apply`：开始实施。AI 将根据任务清单（Tasks）按部就班地编写代码。
- `/opsx:sync`：同步规约。用于将子库的 Delta Spec 更新至主库。
- `/opsx:archive`：任务归档。这是资产沉淀的关键时刻，AI 会引导您执行“资产反哺”。

### 2. Superpowers (Skills) - 肌肉与工程纪律
Superpowers 是本项目底层采用的技能增强系统。它教 AI 如何保持高水准的工程习惯。
- `activate_skill <name>`：激活特定技能（如 `meta-distiller`, `test-driven-development`）。
- **TDD 驱动**：强制“先写测试，后写代码”，确保资产 100% 可运行。
- **安全审计**：由 `meta-safe-executor` 提供的 Git 自动快照记录。

## 🏗️ 目录架构

- **`.gemini/skills/`**：大脑 —— 遵循 TDD 文档标准的原子化技能库。
- **`patterns/`**：图纸 —— 经过参数化处理、具备完整测试覆盖的代码片段。
- **`openspec/`**：治理 —— 负责任务、规约及架构决策记录（ADR）的生命周期管理。

## ⚖️ 致敬与上游依赖 (Credits)

YOU-DRIVE-SOP 是站在巨人肩膀上的作品。我们深度集成了以下杰出的开源工具：

- **[OpenSpec](https://github.com/Fission-AI/OpenSpec)**：由 **Fission-AI** 开发的变更驱动规约系统。它为本项目提供了稳健的生命周期管理底座。
- **[Superpowers](https://github.com/obra/superpowers)**：由 **Jesse (obra)** 发起的 AI 协作技能系统。它为本项目提供了工程纪律的“元逻辑”来源。
- **[Gemini Superpowers](https://github.com/barretstorck/gemini-superpowers)**：由 **Barret Storck** 适配的 Gemini CLI 专用技能集。

*本项目遵循 MIT 协议，并在上述上游工具的基础上建立了 YOU-DRIVE-SOP 专有的自演进与提纯闭环。*

---
*YOU-DRIVE-SOP - 驱动你的智力资产。*

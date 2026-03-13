## Context

我们要把子库的入口文件 `GEMINI.md` 从一份“法律文件”转变为一个“交互仪表盘”。

## Goals

**1. 看板式 `GEMINI.md` 设计**
- 内容：欢迎语、当前链路状态、核心指令集（分类展示）。
- 动态项：母库路径 `{{FOUNDRY_ROOT}}` 的实时填充。

**2. 交互式引导 (Interactive Onboarding)**
- 环节：在初始化技能的 `Final Synthesis` 之后触发。
- 逻辑：提问 -> 接收输入 -> 执行对应的第一个 `activate_skill` 或 `/opsx`。

## Decisions

- **看板位置**：置于子库 `GEMINI.md` 的顶部。理由：用户每次打开会话，AI 读入的第一行就是操作指南。
- **指令分类**：明确划分为“逆向提纯 (Legacy)”与“新功能开发 (Feature)”。

## Risks / Trade-offs

- **[Risk] 指令冗余导致上下文拥挤** → [Mitigation] 仅展示最核心的 3-5 条指令，高级指令引导用户查看 `GETTING_STARTED.md`。

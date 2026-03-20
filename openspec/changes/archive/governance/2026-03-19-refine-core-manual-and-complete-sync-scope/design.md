## Context
手册必须与最新的规约 (Specs) 和技能 (Skills) 保持物理同步。

## Goals
- 手册内容 100% 覆盖最新的安全与同步策略。
- 确保子库初始化后能立即看到手册。

## Decisions
- **章节重构**: 
    - 增加 1.4 物理安全锁 (Git Isolation)。
    - 增加 4.4 链路回退模式 (Hybrid Link)。
- **同步指令**: 在 `xcopy` 列表中显式加入 `SOP_CORE_MANUAL.md`。

## Risks
- **内容冗余**: 需保持手册的高浓度，避免与 specs 重复。

## Why
子库（Workshop）在未配置 `.gitignore` 的情况下链接母库资产，会导致 Git 在切换分支时误删物理链路，并极易穿透 Junction 导致母库源码物理丢失。这是一个最高等级的安全漏洞。

## What Changes
- **强制隔离步**：修改 `workshop-initializing` 技能，将“注入 .gitignore”提升为 **Step 0.5 (前置硬门禁)**。
- **自动检测与追加**：AI 必须自动检测子库是否存在 `.gitignore`，并强制追加 `.gemini/skills/` 和 `patterns/` 目录。
- **安全警告**：在初始化开始前，若检测到无 Git 忽略配置，AI 必须输出红色警报。

## Capabilities
- `git-isolation-sentinel`: 负责子库物理链路的 Git 安全隔离。

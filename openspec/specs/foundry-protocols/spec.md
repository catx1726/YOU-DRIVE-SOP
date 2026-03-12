## ADDED Requirements

### Requirement: 环境指纹识别 (workshop-initializing)
子库对齐 SHALL 包含链路持久化与规约同步。
- 必须包含 Node 20.x, npm 10.x 强制标准检查。
- 必须支持禁止读取清单（Deny-List），防止敏感配置被收割。
- 必须包含关键依赖（如 Vue, React, Vite）的指纹识别。
- 在初始化末尾，必须在子库根目录创建或更新 `GEMINI.md`。
- `GEMINI.md` 必须包含对母库全局标准（Global Standard）的强制引用声明。
- **物理链路**：必须在子库创建 `.gemini/link.json` 记录母库绝对路径。
- **规约同步**：必须将母库的 `openspec/schemas/` 核心协议注入子库本地，确保 OpenSpec 工具能正确执行规约检查。

#### Scenario: 自动化宪法注入
- **WHEN** 子库执行 `workshop-initializing` 成功挂载母库技能后。
- **THEN** 系统自动在子库生成 `GEMINI.md`，并在其中写入：『本项目的 AI 行为流必须遵循母库全局标准 (D:\code\2026\Base-AI-Driven-Template\.gemini\global_standard.md)』。

#### Scenario: 跨库规约可见性
- **WHEN** 子库执行对齐流程。
- **THEN** 系统自动生成 `link.json`，并同步母库的 `openspec/schemas/`（模板）与 `openspec/specs/foundry-protocols/`（主规约）至子库对应目录，确保子库 OpenSpec 工具能正确加载全局规约。

### Requirement: 逻辑提纯协议 (logic_schema)
逻辑提纯 SHALL 具备全局唯一入口并执行标准化存储。
- **唯一执行引擎**：母库体系内所有的资产收割、逻辑提炼动作必须由 `meta-distiller` 技能统一执行。
- **物理标准**：存入 `patterns/` 的每个资产必须包含 `index.ts`, `index.test.ts`, `README.md`。
- **废弃项**：废弃在子库 `openspec/specs/logic.md` 中存储具体代码实现的模式。该文件仅用于逻辑描述，不作为代码资产载体。
- **联动引用**：生成的 `common-` 技能必须包含指向对应 `patterns/` 物理文件的 Markdown 链接。
- **参数化**：所有项目特定词汇必须根据 `env.md` 替换为 `{{VAR_NAME}}`。
- **丰满度标准**：生成的文档必须详实，涵盖 Spec 定义的所有功能点。

#### Scenario: 从旧项目逆向收割
- **WHEN** AI 使用 `legacy-extractor` 识别出一段高价值业务代码。
- **THEN** AI 禁止在本地 `logic.md` 中展开代码，而是引导用户激活 `meta-distiller` 将该资产反哺至母库。

### Requirement: 架构决策协议 (decision_schema)
架构决策协议 SHALL 规范 ADR 的编写格式，确保所有演进记录均包含完整的背景和后果评估。
- ADR 必须包含 Status (Proposed, Accepted, etc.)。
- 必须包含 Consequences 字段。
- 必须支持关联子库（Related Project）字段。

#### Scenario: 记录跨库技术妥协
- **WHEN** 在子库中因为旧版 Webpack 限制而选择了替代方案。
- **THEN** 系统依据 `decision_schema` 在子库生成一份 ADR，详细记录该妥协的背景及其对母库资产同步的影响。

### Requirement: 生产安全审计 (Production Safety Audit)
系统 SHALL 对所有物理写操作执行实时审计与熔断保护。
- **操作日志**：子库必须维护 `.gemini/ops_changelog.md` 记录每次操作的时间、意图及撤销指令。
- **安全熔断**：破坏性操作（DELETE, MOVE）必须强制弹窗确认。
- **Git 快照**：写操作前必须确保当前状态已 Commit。

#### Scenario: 误删恢复
- **WHEN** AI 执行了错误的删除指令。
- **THEN** 用户通过读取 `ops_changelog.md` 中的撤销指令或 Commit ID，能够瞬间回滚。

### Requirement: 归档门禁 (openspec-changes-archive)
归档流程 SHALL 执行管理档案与执行记录的物理分流存储。
- **分流存储**：
    - `Proposal/Design` 归档至 `archive/governance/`。
    - `Ops Changelog` 归档至 `openspec/operations/archive/`。
- **合并决策**：若发现暂存资产，必须强制询问用户是否将其并入母库。

#### Scenario: 审计分离归档
- **WHEN** 执行 `/opsx:archive`。
- **THEN** 系统自动将任务文件夹移入治理归档区，同时将操作日志移入操作审计区。

### Requirement: 链接自愈 (Link Self-Healing)
系统 SHALL 能够自动识别并修复子库中失效的技能映射。
- **属性识别**：必须能够通过 `ReparsePoint` 属性识别物理联接点（Junction）。
- **幂等清理**：在重建链接前，SHALL 安全移除现有的联接点，同时严格保护 non-linked 的本地文件夹（如 `openspec-bridge`）。
- **物理重建**：使用 `Junction` 类型重建从子库到母库技能的一对一映射。

#### Scenario: 一键修复损坏的链接
- **WHEN** 用户发出“修复链接”或“刷新技能”指令。
- **THEN** AI 识别当前工作区所有属性为 `ReparsePoint` 的子文件夹，执行安全清理，并根据 `link.json` 定义的母库路径重建所有技能的 Junction 映射。

### Requirement: 分步执行协议 (Step-by-Step Execution)
分步执行 SHALL 包含滚动式上下文聚合机制以保证产出质量。
- **任务规划**：在开始前，必须生成一份临时任务列表。
- **状态持久化**：必须在 `.gemini/skill_progress.md` 中实时记录完成状态。
- **步前读回**：在执行任何涉及文档、规约、代码资产生成的任务步前，AI 必须显式执行 `read_file` 以读取当前已生成的全量内容。
- **终期审计步**：复杂技能的任务列表末尾必须包含一个“终期质量审计”任务，负责全局逻辑梳理与文字丰满。

#### Scenario: 长文档生成的质量保鲜
- **WHEN** AI 执行到长文档生成技能的第 3 步（如：编写 Implementation 章节）。
- **THEN** AI 必须先读取已完成的 Step 1 & 2 的文字内容，确保 Step 3 的术语与前文保持一致。

### Requirement: 品牌与脱敏 (Rebranding & Sanitization)
所有文档与代码 SHALL 遵循 `YOU-DRIVE-SOP` 品牌标准并执行脱敏。
- **禁止硬编码**：禁止出现任何特定于开发者的物理绝对路径（如 `D:\`）。
- **去组织化**：移除个人或组织特定标识，统一替换为 “Foundry”、“Workshop” 或 “Core Library”。
- **术语一致性**：资产处理动作必须使用 “Distillation”（提纯）与 “Contribution”（反哺）。

#### Scenario: 开源化文档生成
- **WHEN** AI 生成 README。
- **THEN** 系统自动使用 `YOU-DRIVE-SOP` 品牌头，并以“驾驶者（You）”为中心进行叙述。

### Requirement: 路径自动探测 (Path Discovery)
系统 SHALL 具备自动定位资源根目录的能力。
- **动态占位符**：所有的 Skill 引用必须使用 `{{FOUNDRY_ROOT}}` 占位符。
- **探测逻辑**：AI 必须首先执行根目录探测逻辑（如向上递归寻找 .gemini/global_standard.md），获取物理路径并实时填充占位符。

#### Scenario: 跨环境执行
- **WHEN** 在一个新的 Linux 环境下部署本库。
- **THEN** AI 自动识别出当前的母库根目录，无需用户修改 Skill 源码。

### Requirement: 文档亲和力 (Documentation Affinity)
开源文档 SHALL 兼顾国际化展示与本地化深度。
- **中文优先**：在针对中文用户的分发版本或主仓库中，核心逻辑说明必须包含准确的中文翻译。
- **术语对照**：文档必须提供关键工程术语的对照表（如：Distillation -> 提纯）。

### Requirement: 工具链透传 (Toolchain Disclosure)
README 与入门指南 SHALL 完整覆盖核心工具的操作逻辑。
- **OpenSpec 指引**：必须解释 Propose -> Apply -> Archive 的状态流转。
- **Superpowers 指引**：必须解释 Skill 的激活方式（activate_skill）及 TDD 强制要求。

#### Scenario: 新手快速驱动
- **WHEN** 用户首次打开 README。
- **THEN** 用户能通过文档快速区分“什么是治理（OpenSpec）”和“什么是执行（Superpowers）”，并能找到第一条该输入的指令。

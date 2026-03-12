# SOP 2.0 环境指纹协议 (env_schema)

## 1. 强制运行环境 (Runtime Standard)
- **Node.js**: `>=20.10.0` (母库基准)。
- **npm**: `>=10.0.0`。
- **OS**: Cross-platform (Windows/Linux/macOS)。

## 2. 关键依赖指纹 (Dependency Fingerprints)
| 类别 | 库/引擎 | 推荐版本 (Foundry) | 备注 |
| :--- | :--- | :--- | :--- |
| Framework | `vue` | `^3.4.0` | Vue 2 项目需记录偏差 |
| Build Tool | `vite` | `^5.0.0` | Webpack 项目需记录转换成本 |
| Testing | `vitest` | `^1.0.0` | 强制 TDD 运行环境 |
| Runtime | `typescript` | `^5.0.0` | 建议全量 TS 化 |

## 3. 环境偏差评估 (Gap Analysis)
所有子库生成的 `env.md` 必须包含以下评估项：
- **Node 版本偏差**：如果是 Node 16/14，必须标注收割逻辑的 Polyfill 需求。
- **构建工具偏差**：Webpack 3/4 的旧逻辑在提纯时需解耦 CommonJS 语法。
- **架构模式偏差**：如从 Options API 向 Composition API 的迁移评估。

## 4. 禁止读取/收割清单 (Deny-List)
- `.env` (包含密钥)。
- `*.pem`, `*.key` (证书)。
- `dist/`, `node_modules/` (构建产物)。
- `secrets.json` 或业务私有配置文件。

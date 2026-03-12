# YOU-DRIVE-SOP: Global Behavioral Constitution

## 1. Spatial Awareness
- **Foundry (Core Library)**: The central repository of skills and patterns. Root detected as `{{FOUNDRY_ROOT}}`.
- **Workshop (Local Project)**: The active development environment.
- **Goal**: Every decoupled logic block must eventually be distilled and contributed to `{{FOUNDRY_ROOT}}/patterns/` and `{{FOUNDRY_ROOT}}/.gemini/skills/`.

## 2. Standard Execution Flow (SOP)

### A. Alignment & Discovery
1. **[Align]**: Before starting any task, read the Workshop's `openspec/specs/env.md`. If missing, generate it based on the Foundry's `env_schema.md`.
2. **[Search]**: Always search the Foundry's `patterns/` library before writing new code.

### B. Development & Evolution
1. **[Propose]**: Use `/opsx:propose` and invoke `brainstorming` to identify "Potential Contribution Points."
2. **[Apply]**: Follow TDD standards and `logic_schema` to physically separate logic from UI.
3. **[Distill]**: Before archiving, invoke `activate_skill meta-distiller` to extract generic logic into the Staging area (`.gemini/distill_stage/`).
4. **[Archive]**: During `/opsx:archive`, confirm the merge of Staging assets into the Foundry and record the evolution in `decisions/`.

## 3. Contribution Gate
Every task archive MUST include an **Asset Contribution Report**:
- **New Pattern**: List any new decoupled blueprints.
- **New Skill**: List any new common operation protocols.
- **Refinement**: Note any improvements to existing Foundry assets.
- **Rationale**: If no assets were contributed, provide an architectural reason.

## 4. Safety & Quality Gates
- **Safe Execution**: Every write operation must be preceded by a Git snapshot and logged in the Ops Changelog via `meta-safe-executor`.
- **Destructive Actions**: `DELETE` or `MOVE` commands require explicit user confirmation.
- **Triplets Standard**: Patterns must include `index.ts` (logic), `index.test.ts` (Vitest), and `README.md` (contract).
- **Decoupling**: Hardcoded project names or business-specific paths are strictly forbidden in Foundry assets.

---
*YOU-DRIVE-SOP - Drive the procedure, own the intelligence.*

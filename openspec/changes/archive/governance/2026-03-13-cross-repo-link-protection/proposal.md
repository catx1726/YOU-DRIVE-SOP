## Why

Physical links (Junctions) in the YOU-DRIVE-SOP framework are susceptible to "penetrative deletion" when users switch branches or run `git clean` in sub-projects (Workshop). This poses a significant risk to the integrity of the Foundry's core assets (Skills/Patterns).

## What Changes

- **Git-Ignore Enforcement**: Automatically add `.gemini/skills/` to the sub-project's `.gitignore` during initialization to isolate it from Git's destructive operations.
- **Constitutional Update**: Formalize the "Cross-Repo Link Protection" protocol in the global standard.
- **Audit Logging**: Ensure every link-related action is tracked with precise local timestamps.

## Capabilities

### New Capabilities
- `cross-repo-safety`: Defines rules for safe multi-repo linkage and automated protection.

### Modified Capabilities
- `foundry-protocols`: Update requirements to mandate Git-ignore based isolation for all junctions.

## Impact

- **Affected Code**: `workshop-initializing/SKILL.md`, `.gemini/global_standard.md`.
- **Reliability**: Eliminates the risk of Foundry asset loss during sub-project development cycles.

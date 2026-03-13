## Context

The YOU-DRIVE-SOP framework currently relies on manual intervention for branch management and toolchain verification. This design automates these steps using `gh` CLI and a new bootstrapping logic in `workshop-initializing`.

## Goals / Non-Goals

**Goals:**
- Automate `git checkout -b issue-N` based on the current change context.
- Enforce toolchain prerequisites (`gh`, `@fission-ai/openspec`) during initialization.
- Automate PR summary generation into the `archive` flow.
- Standardize sub-project configuration via `config_foundry.yaml` patching.

**Non-Goals:**
- Replacing `git` or `gh` with custom implementations.
- Managing GitHub Actions directly (handled by the PR template).

## Decisions

- **Decision 1: Use `gh` CLI for VCS integration.**
  - **Rationale**: Industry standard, cross-platform, and easily auditable in `ops_changelog.md`.
  - **Alternatives**: Using Node-based Octokit (increased dependency weight, harder to audit via CLI).
- **Decision 2: Sub-project Bootstrapping via Patching.**
  - **Rationale**: `openspec init` provides the base, and our `patch` adds the SOP 2.0 "Foundry Context". This allows for project-specific customization while maintaining global standards.
- **Decision 3: PR Summary as an Archive Artifact.**
  - **Rationale**: Linking the task reflection directly to the PR ensures that the PR description is always high-signal and accurate.

## Risks / Trade-offs

- [Risk] User doesn't have `gh` CLI installed. → [Mitigation] Automated pre-check in `workshop-initializing` with clear installation guide.
- [Risk] Conflict between `config_foundry.yaml` and existing `config.yaml`. → [Mitigation] Use a non-destructive merging strategy that prioritizes SOP 2.0 mandatory fields (context, rules, skills).

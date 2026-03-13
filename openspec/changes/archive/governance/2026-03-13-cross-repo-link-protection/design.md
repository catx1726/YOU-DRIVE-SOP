## Context

Sub-projects link to Foundry assets via Windows Junctions. Git by default may attempt to clean or modify these paths if they aren't explicitly ignored, potentially leading to accidental deletion of the original Foundry source files.

## Goals / Non-Goals

**Goals:**
- Implement "Scheme A: Git-Ignore strategy" to ensure silent protection of linked directories.
- Automate the `.gitignore` update during the `workshop-initializing` skill.

**Non-Goals:**
- Modifying Git's core internal behavior.
- Using complex pre-checkout hooks (prioritizing the simpler and more robust ignore strategy).

## Decisions

- **Decision 1: Use .gitignore for Isolation.**
  - **Rationale**: It's the most standard and portable way to tell Git to "hands off" a specific directory. It prevents `git checkout` and `git clean` from touching the linked files.
- **Decision 2: Automated Injection during Init.**
  - **Rationale**: Ensures that every sub-project is protected from the very moment it is linked to the Foundry.

## Risks / Trade-offs

- [Risk] User manually removes the ignore rule. → [Mitigation] The `workshop-initializing` skill will re-verify and re-inject the rule every time it is run (idempotent).

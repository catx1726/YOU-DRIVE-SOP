## Why

Currently, the YOU-DRIVE-SOP framework has a gap between the theoretical SOP 2.0 standard and actual VCS execution. Manual branch switching, issue creation, and PR summary generation lead to process inconsistency and human error. We need to automate the GitHub issue-to-archive loop to ensure 100% compliance with the SOP1 legacy and SOP 2.0 standards.

## What Changes

- **Automated VCS Hook**: Implement automatic GitHub issue detection and branch switching (`issue-N`) during the `propose` phase.
- **Toolchain Self-Healing**: Enforce `gh` CLI and OpenSpec package checks during `workshop-initializing`.
- **PR Closure Automation**: Generate standardized PR summaries and closure commands during the `archive` phase.
- **Config Patching**: Introduce `config_foundry.yaml` as a base template for sub-project bootstrapping.

## Capabilities

### New Capabilities
- `vcs-lifecycle-automation`: Covers GitHub issue linking, branch management, and PR summary generation logic.
- `toolchain-bootstrapping`: Manages the automated installation check and configuration patching for OpenSpec and GitHub CLI.

### Modified Capabilities
- `foundry-protocols`: Update the `openspec-changes-archive` requirement to include mandatory PR summary and closure logic.

## Impact

- **Affected Code**: `.gemini/skills/workshop-initializing/`, `.gemini/skills/meta-distiller/`, `openspec/config.yaml`.
- **Dependencies**: Requires `gh` CLI (GitHub CLI) and `@fission-ai/openspec` to be installed on the host system.
- **System**: Enhances the reliability of the "Double Verification" gate and asset distillation flow.

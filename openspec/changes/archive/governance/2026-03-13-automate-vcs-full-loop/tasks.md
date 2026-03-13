## 1. Toolchain & Config Bootstrapping

- [x] 1.1 Update `workshop-initializing/SKILL.md` with `gh` and `@fission-ai/openspec` pre-checks.
- [x] 1.2 Implement the automated config patching logic in `workshop-initializing` (Merge `config_foundry.yaml` to local `config.yaml`).
- [x] 1.3 Ensure `config_foundry.yaml` is physically present in the `openspec/` root.

## 2. VCS Lifecycle Automation

- [x] 2.1 Update `common-uniapp-vue2/SKILL.md` (and generic domain skills) to include automatic `git checkout -b issue-N` steps.
- [x] 2.2 Enhance `meta-distiller` and `archive` flow to generate the standardized PR Summary output.
- [x] 2.3 Inject `.github/PULL_REQUEST_TEMPLATE.md` into the `workshop-initializing` flow.

## 3. Validation & Integration

- [x] 3.1 Perform a dry-run of the full loop: Propose -> Apply -> Archive -> PR.
- [x] 3.2 Verify that `ops_changelog.md` captures all automated VCS actions.
- [x] 3.3 Merge `automate-vcs-full-loop` delta specs into the main `foundry-protocols/spec.md`.

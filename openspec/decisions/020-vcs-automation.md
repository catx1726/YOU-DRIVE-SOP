## ADR 020: Automated VCS & Bootstrapping Protocol

### Context
SOP 2.0 needs a seamless bridge between local task management (OpenSpec) and remote version control (GitHub). Sub-projects often lack standardized configurations and toolchain verifications.

### Decision
1.  **Mandatory VCS CLI**: Use `gh` CLI as the primary interface for issue/branch/PR automation.
2.  **Config Patching**: Use `config_foundry.yaml` as a base template to be merged during sub-project initialization.
3.  **Automated Summary**: Integrate PR summary generation directly into the `archive` flow.

### Status
Accepted

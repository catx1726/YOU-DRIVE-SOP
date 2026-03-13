## ADR 019: Double Verification Gate

### Context
Asset distillation (Meta-Distiller) needs higher reliability when moving from Workshop to Foundry.

### Decision
Implement a "Double Verification" gate:
1. **Local Pre-verify**: Must pass tests in the sub-repo.
2. **Foundry Re-verify**: Must pass tests in the main repo during the 'Accept' phase.

### Status
Accepted

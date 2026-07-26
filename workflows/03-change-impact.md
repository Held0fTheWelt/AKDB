# Workflow: change impact

Before a planned change, AKDB can assemble related decisions, diagrams, source areas, symbols, and known constraints.

## Planned change

Replace the current session store.

## Impact view

- Decisions: ADR-002, ADR-009
- Components: `SessionRepository`, `AuthService`, API gateway
- Diagrams: runtime session flow, deployment context
- Constraints: provider independence, token handling, migration compatibility
- Review owners: platform architecture, security

The purpose is to make hidden architectural consequences visible before implementation begins.

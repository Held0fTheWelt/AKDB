# Workflow: change impact

Before a planned change, AKDB can assemble related decisions, diagrams, source areas, symbols, and known constraints.

This scenario is synthetic; the identifiers below do not refer to a customer project.

## Planned change

Replace the current session store.

## Impact view

- Decisions: ADR-002, ADR-009
- Components: `SessionRepository`, `AuthService`, API gateway
- Diagrams: runtime session flow, deployment context
- Constraints: provider independence, token handling, migration compatibility
- Review owners: platform architecture, security

## Review the evidence

Follow each relationship back to its source and check the source baseline. Separate
an explicitly recorded dependency from an inferred relationship. Record missing
coverage, stale information and conflicting decisions before deciding the change scope.

The impact view is a review aid, not proof that all architectural consequences have
been found. A source-bound result is easier to inspect, but still needs engineering
judgment. A wider automated remedy workflow must not be inferred from this example.

# Workflow: agent context pack

## Request

> Add a second authentication provider without violating the existing architecture.

## Context delivered

- ADR-004: authentication must remain provider-independent.
- ADR-009: provider-specific code must stay outside the domain layer.
- Relevant components: `AuthService`, `SessionRepository`, `ProviderAdapter`.
- Relevant diagram: `authentication-context.puml`.
- Guardrail: tokens must not be persisted in gameplay-facing modules.

## Review signals

- The current diagram does not show the provider adapter boundary.
- One document still references a retired provider interface.
- The proposed change affects two documented module boundaries.

The result is a bounded, source-anchored context pack rather than a broad dump of project text.

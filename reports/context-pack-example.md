# Example: context pack

**Task:** Add a second authentication provider.

**Authoritative decisions:** ADR-004, ADR-009

**Affected areas:** `AuthService`, `ProviderAdapter`, `SessionRepository`

**Constraints:** provider-independent domain layer; no token persistence in gameplay-facing modules.

**Warnings:** one diagram is stale; one interface reference is deprecated.

**Recommended review:** platform architecture and security.

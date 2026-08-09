# Example: change-impact report

**Planned change:** Replace the current session store.

**Affected decisions:** ADR-002, ADR-009

**Affected components:** `SessionRepository`, `AuthService`, API gateway.

**Primary risk:** a storage change may introduce provider-specific assumptions into the domain layer.

**Candidate write set:** session-store adapter and migration tests; domain policy remains excluded.

**Required evidence:** session-contract tests, migration check, architecture-owner review.

**Next step:** review the migration boundary with the platform architecture owner before implementation.

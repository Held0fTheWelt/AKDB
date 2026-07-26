# Workflow: architecture drift

AKDB compares architectural knowledge with available project evidence and surfaces reviewable signals.

Example findings:

| Severity | Finding | Evidence |
| --- | --- | --- |
| High | Documented module boundary no longer matches source paths | `ADR-009`, `src/domain/`, recent Git history |
| Medium | Diagram omits a dependency introduced by a later change | `authentication-context.puml`, `AuthService` |
| Low | Definition uses an outdated component name | glossary, source symbol index |

These are review signals for the architecture owner, not automatic mutations of the source repository.

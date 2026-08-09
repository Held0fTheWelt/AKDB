# Example: governed change evidence summary

**Synthetic task:** Replace the session-store adapter.

**Sealed baseline:** repository revision and architecture-context revision recorded before work.

**Allowed write set:** adapter implementation and adapter tests.

**Lease result:** granted; no overlapping active write set detected.

**Evidence gates:**

| Gate | Result | Evidence |
| --- | --- | --- |
| Scope | Pass | Changed paths remain inside the declared write set |
| Tests | Pass | Adapter and session-contract checks completed |
| Architecture | Review required | Storage migration note needs human confirmation |
| Promotion | Pending | Human reviewer decision required |

**Agent authority:** execution and evidence submission only; no self-promotion.

**Recovery link:** rollback procedure recorded for reviewer approval.

This example is illustrative. It is not a customer result, production SLA, or claim of autonomous
Git merge execution.

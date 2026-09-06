# Example: governed change evidence summary

**Synthetic task:** Replace the session-store adapter.

**Sealed baseline:** repository revision and architecture-context revision recorded before work.

**Plan binding:** approved plan revision and adapter-replacement work package recorded.

**Allowed write set:** adapter implementation and adapter tests.

**Declared impact:** session persistence behavior and adapter wiring; authentication policy and
token handling remain outside scope.

**Lease result:** granted; no overlapping active write set detected.

**Evidence gates (illustrative values, not an executed test receipt):**

| Gate | Result | Evidence |
| --- | --- | --- |
| Scope | Pass | Changed paths remain inside the declared write set |
| Delivery binding | Pass | Change is linked to the approved plan revision and work package |
| Tests | Pass | Adapter and session-contract checks completed |
| Architecture | Review required | Storage migration note needs human confirmation |
| Promotion | Pending | Human reviewer decision required |

**Agent authority:** execution and evidence submission only; no self-promotion.

**Recovery link:** rollback procedure recorded for reviewer approval.

**Re-examination:** the session-storage decision and deployment view are marked as potentially
affected; the verdict records the evidence it examined.

This example is illustrative. It is not a customer result, production SLA, or claim of autonomous
Git merge execution.

## Reader-facing interpretation

The example change remains pending. The illustrative passing scope and test rows do
not override the unresolved architecture review or supply a human promotion decision.
The reader can inspect the source references and request the missing migration
evidence. Missing evidence must remain visible rather than being summarized as an
all-green result.

# Workflow: governed agent change

This synthetic example shows the bounded pilot control model. It does not represent a customer
project or an autonomous Git merge.

## Request

> Replace the session-store adapter without changing authentication policy or token handling.

## Sealed task scope

- Repository baseline: recorded before execution
- Architecture context: affected decisions, constraints, diagrams, and source areas
- Plan binding: approved plan revision and work package
- Declared impact: session persistence behavior and adapter wiring
- Permitted paths: adapter implementation and its tests
- Excluded paths: domain policy, token handling, deployment configuration
- Review owner: a human platform-architecture reviewer

## Control path

1. The task receives an explicit write set and a bounded lease.
2. A conflicting task targeting the same paths is rejected while that lease is active.
3. The agent records change, lineage, invalidation footprint, and validation evidence but cannot
   approve its own promotion.
4. Required tests and architecture checks are evaluated as gates, with the examined evidence
   retained alongside the verdict.
5. A human reviewer accepts, rejects, or requests revision.
6. The decision retains a linked recovery or rollback path and the affected knowledge is queued for
   re-examination.

## Fail-closed examples

- Expired or revoked lease: change is not eligible for promotion.
- Overlapping write set: conflicting work is not leased concurrently.
- Missing or failed evidence gate: human promotion is blocked.
- Agent promotion attempt: rejected; the decision remains human-owned.

The output is a reviewable evidence package around a bounded change, not a promise that every direct
filesystem or database mutation is technically impossible.

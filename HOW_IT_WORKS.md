# How AKDB works

AKDB is used as a knowledge and review layer around the sources that remain authoritative in a project.

```text
Project sources
    ├── ADRs and architecture documents
    ├── UML, PlantUML, and Mermaid
    ├── rules, definitions, and structured files
    └── registered repository and Git evidence
              │
              ▼
      Structured architecture knowledge
              │
       ┌──────┴──────────────┐
       ▼                     ▼
   Read and review       Governed pilot change
   ├── Search            ├── Sealed task scope
   ├── Drift             ├── Lease + write set
   ├── Context packs     ├── Evidence gates
   └── Change impact     └── Human decision
       │                     │
       └──────────┬──────────┘
                  ▼
         Reviewable engineering work
```

AKDB does not replace the repository, documentation, or architecture owner. It relates and evaluates knowledge so that people and coding agents can use it before a change is made.

## Typical loop

1. Register the project sources.
2. Build or refresh the architecture knowledge view.
3. Ask for context for a concrete engineering task.
4. Review decisions, constraints, relationships, and drift signals.
5. Make the change in the owning source files.
6. Reconcile the knowledge view after the change.

## Governed pilot loop

For a deliberately bounded agent-assisted change, the reviewed internal pilot profile adds a
control path around the engineering work:

1. Seal the repository baseline and the architecture context used for the task.
2. Define the permitted project, repository, tools, paths, and write set.
3. Issue a bounded lease for non-conflicting work.
4. Collect run events and required evidence from the change.
5. Evaluate explicit review and validation gates.
6. Require a human decision before the change can enter the promotion state.
7. Preserve the decision and a linked recovery or rollback path.

Overlapping write sets, expired or revoked leases, missing evidence, failed gates, and agent-side
promotion attempts are rejected in this profile. This is a supervised pilot control model, not a
claim that AKDB autonomously merges arbitrary Git changes or can prevent a database administrator
from bypassing every application-level control.

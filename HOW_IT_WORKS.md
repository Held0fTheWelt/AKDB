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
       ┌──────┼────────┐
       ▼      ▼        ▼
   Search   Drift   Context packs
       │      │        │
       └──────┴────────┘
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

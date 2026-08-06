# ArchitecturalKnowledgeDB — Public Showcase

ArchitecturalKnowledgeDB (AKDB) is a proprietary, local-first architecture knowledge layer for software projects and coding agents.

This repository is the public showcase for AKDB. It demonstrates the problems addressed, the workflows supported, and the kinds of outputs teams can receive. It does **not** contain the AKDB implementation, private source code, customer data, or the internal operating model.

## Current status

**Status date: 6 August 2026.** AKDB has a substantial, testable internal engineering baseline with
project-scoped architecture knowledge, source provenance, search and context assembly, drift and
change-impact analysis, SQLite/PostgreSQL storage paths, and CLI, API, and MCP access. Current work
extends that baseline with governed write authority, supervised agent execution, recovery,
observability, secret handling, and repeatable release validation.

AKDB is an engineering preview, not a generally available production product. Internal technical
breadth has been demonstrated; operation on an independent customer repository, external security
review, repeatable delivery, and product-market evidence have not yet been demonstrated. See
[Status and Outlook](STATUS_AND_OUTLOOK.md) for the evidence boundary, release gates, and roadmap.

## The problem

Software architecture knowledge is distributed across ADRs, diagrams, documentation, source trees, Git history, rules, and team memory. A search result or an LLM context window does not tell you which information is authoritative, what it affects, or whether it is still valid.

## What AKDB provides

- Source-anchored architecture context for engineers and coding agents
- Relationships between decisions, diagrams, source areas, symbols, and provenance
- Drift and stale-knowledge signals across documentation and the current system
- Compact, task-specific context packs instead of undifferentiated prompt dumps
- Reviewable change-impact and architecture-review outputs
- Local-first operation suitable for sensitive or long-lived software projects

## Explore the showcase

- [Why AKDB](WHY_AKDB.md)
- [How the approach works](HOW_IT_WORKS.md)
- [Example workflows](workflows/README.md)
- [Example outputs](reports/README.md)
- [Client outcomes](CLIENT_OUTCOMES.md)
- [Status and outlook](STATUS_AND_OUTLOOK.md)

## Services

AKDB is developed and delivered as part of independent software architecture and AI engineering services. Typical engagements include architecture knowledge assessments, project onboarding, drift analysis, agent-context integration, and ongoing architecture knowledge maintenance.

For implementation, integration, or a project-specific assessment, contact the author directly.

## Public disclosure boundary

Everything in this repository is intentionally approved for public disclosure. It contains no
trade secrets, credentials, customer data, or non-public implementation source. AKDB remains
proprietary technology; the descriptive material and synthetic examples in this showcase do not
grant access to the implementation and do not represent customer projects.

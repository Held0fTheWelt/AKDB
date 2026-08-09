# ArchitecturalKnowledgeDB — Public Showcase

ArchitecturalKnowledgeDB (AKDB) is a proprietary, local-first architecture knowledge layer for software projects and coding agents.

This repository is the public showcase for AKDB. It demonstrates the problems addressed, the workflows supported, and the kinds of outputs teams can receive. It does **not** contain the AKDB implementation, private source code, customer data, or the internal operating model.

## Current status

**Status date: 10 August 2026.** The packaged baseline remains version `0.3.0`. The latest reviewed,
versioned internal implementation (through 8 August 2026) extends its project-scoped architecture
knowledge, provenance, search, context assembly, drift, and change-impact workflows with a governed
pilot path for supervised agent changes, append-only knowledge revision history, recovery evidence,
observability, and reproducible packaging controls.

AKDB is an engineering preview, not a generally available production product. These post-`0.3.0`
capabilities are internal, unreleased evidence rather than shipped promises. Operation on an
independent customer repository, external security review, repeatable customer delivery, and
product-market evidence have not yet been demonstrated. See
[Status and Outlook](STATUS_AND_OUTLOOK.md) for the evidence boundary, release gates, and roadmap.

## The problem

Software architecture knowledge is distributed across ADRs, diagrams, documentation, source trees, Git history, rules, and team memory. A search result or an LLM context window does not tell you which information is authoritative, what it affects, or whether it is still valid.

## What AKDB provides

- Source-anchored architecture context for engineers and coding agents
- Relationships between decisions, diagrams, source areas, symbols, and provenance
- Drift and stale-knowledge signals across documentation and the current system
- Compact, task-specific context packs instead of undifferentiated prompt dumps
- Reviewable change-impact and architecture-review outputs
- A bounded governed-change pilot path with explicit scope, leases, evidence gates, and human approval
- Local-first operation suitable for sensitive or long-lived software projects

## What is demonstrated internally

- The core knowledge model and its CLI, API, and MCP read workflows are implemented and testable.
- A defined pilot profile can control parallel agent changes through sealed repository/context
  snapshots, explicit write sets, leases, evidence gates, and human promotion decisions.
- A reference scenario and a synthetic load scenario with five separate human principals and five
  agents are automated for both SQLite and PostgreSQL.
- Overlapping write sets, expired or revoked leases, failed gates, and agent-side promotion attempts
  are handled fail-closed in that defined profile.
- Local validation covers full-text search, drift analysis, the governed-change cycle, packaging,
  dependency evidence, and isolated recovery/reconciliation.

This is implementation evidence from maintainer-controlled and synthetic environments. It is not a
claim of customer validation, production readiness, ROI, compliance certification, or universal
protection against administrators and direct database access.

## Explore the showcase

- [Why AKDB](WHY_AKDB.md)
- [How the approach works](HOW_IT_WORKS.md)
- [Example workflows](workflows/README.md)
- [Example outputs](reports/README.md)
- [Client outcomes](CLIENT_OUTCOMES.md)
- [Status and outlook](STATUS_AND_OUTLOOK.md)

## Services

AKDB is developed and delivered as part of independent software architecture and AI engineering
services. Typical engagements include architecture knowledge assessments, project onboarding,
drift analysis, agent-context integration, governed pilot preparation, and ongoing architecture
knowledge maintenance.

For implementation, integration, or a project-specific assessment, contact the author directly.

## Public disclosure boundary

Everything in this repository is intentionally approved for public disclosure. It contains no
trade secrets, credentials, customer data, or non-public implementation source. AKDB remains
proprietary technology; the descriptive material and synthetic examples in this showcase do not
grant access to the implementation and do not represent customer projects.

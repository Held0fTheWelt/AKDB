# ArchitecturalKnowledgeDB and the tooling around it — Public Showcase

ArchitecturalKnowledgeDB (AKDB) is a proprietary, local-first architecture knowledge layer for
software projects and coding agents. It is the centre of a small stack of tools that share one idea:
architecture knowledge should be a **record** that can be queried, related, and checked — not a pile
of documents that happen to describe a system.

This repository is the public showcase for AKDB and that surrounding tooling. It describes the
problems addressed, the capabilities, the workflows supported, and the kinds of outputs teams can
receive. It does **not** contain implementation source, private repositories, customer data,
commercial terms, or the internal operating model.

> Tiny Tool Development also publishes a separate line of Unreal Engine editor plugins through
> Epic Games' Fab marketplace. That product line has its own documentation and is not covered here.

## Current status

**Status date: 28 August 2026.** The packaged AKDB baseline remains version `0.3.0`. The current
governed work is P0 (`plan-akdb-p0-truth-integrity`, revision 7, approved) on pin
`p0/plan-pin-f4129d7`. Waves 1–5 of that plan are merged onto the pin. P0 is not complete; later P0
waves are not done. P1 is locked until P0 completes and the C1–C5 bundle is revised. Later phases,
including P6, are not in progress. This page does not claim that CI is green.

The latest reviewed, versioned internal implementation extends project-scoped architecture knowledge,
provenance, search, context assembly, drift, and change-impact workflows with a governed pilot path
for supervised agent changes, append-only knowledge revision history, recovery evidence,
observability, and reproducible packaging controls. Those capabilities remain engineering-preview
work, not a declared broader release.

AKDB is an engineering preview, not a generally available production product. The tools described
below are internal implementations at varying maturity, from running systems to stated target
architecture. Everything on this page distinguishes the two. Operation on an independent customer
repository, external security review, repeatable customer delivery, and product-market evidence have
not yet been demonstrated. See [Status and Outlook](STATUS_AND_OUTLOOK.md) for the P0 pin record, the
named exceptions, the evidence boundary, and the outlook.

## The problem

Software architecture knowledge is distributed across ADRs, diagrams, documentation, source trees,
Git history, rules, and team memory. A search result or an LLM context window does not tell you which
information is authoritative, what it affects, or whether it is still valid.

Coding agents make this sharper rather than softer. An agent can propose more changes per day than a
small team can review, and it will happily act on a document that stopped being true six months ago.
The constraint is not how fast changes can be produced. It is how many can be understood, checked,
and approved.

## The stack

The pieces are separable. AKDB is useful on its own; each layer above it adds a capability without
becoming a precondition for the one below.

**[ArchitecturalKnowledgeDB](WHY_AKDB.md) — the knowledge layer.**
Project-scoped architecture knowledge: decisions, rules, diagrams, source areas, symbols,
definitions, provenance, and the relations between them. Search, task-specific context assembly,
drift and stale-knowledge signals, change-impact analysis, read-only Git evidence. SQLite and
PostgreSQL storage paths; CLI, API, and MCP access over the same knowledge.

**ContextOps — the control plane.**
Compiles and executes work *from* canonical knowledge while never becoming an alternative authority
for it. Live operational truth is PostgreSQL; jobs, runs, and leases are the execution ledger.
Bounded agent work runs under an external-host protocol: the server does not start agent processes
as children, and hosts pull work through `/agent-hosts/claims` rather than an in-process `/dispatch`.
Hosts register, claim queued work under a lease, heartbeat, emit idempotent events, and complete or
fail explicitly. Around that sit attention and read-tier policies, an append-only ledger, participant
presence and floor coordination, and structured team-meeting contracts.

**Agent Collaboration Plane — the access model.**
One client-agnostic MCP layer so that any agent — Claude Code, Codex, Cursor, or another MCP client —
can read project knowledge cheaply and propose changes, while a human remains the deciding authority.
The point is deliberately narrow: cheap reads, expensive writes, and no agent that can promote its
own work.

**Tiny Tool Observatory — the evidence view.**
A local workbench that turns repository, agent, package, architecture-document, UML, and AKDB
evidence into one queryable project view. It does not replace the producers of that evidence; it
preserves their results and makes the current and historical state inspectable in one place.

**The documentation pipeline — records instead of documents.**
Architecture descriptions, specifications, and product facts live in one authority; published
artefacts are compiled from it rather than written by hand. Automated gates refuse a change that
would reduce traceability, silently drop a derived section, or let an export drift away from the
record. A check that cannot prove its property fails closed rather than warning.

**Augmented Operator — stated direction, not a capability.**
A target architecture for making the operator functions of ContextOps and the Observatory usable as
spatial Meta Quest workflows, with the headset owning its runtimes, local data, and interaction
state, and existing instances available as optional remote providers. Its implementation status is
*not created*. It is listed here because this page is also meant to say what is intended, and it is
marked so that nobody mistakes intent for delivery.

## What this makes possible

- Source-anchored architecture context for engineers and coding agents
- Relationships between decisions, diagrams, source areas, symbols, and provenance
- Drift and stale-knowledge signals across documentation and the current system
- Compact, task-specific context packs instead of undifferentiated prompt dumps
- Reviewable change-impact and architecture-review outputs
- A bounded governed-change path with explicit scope, leases, evidence gates, and human approval
- Local-first operation suitable for sensitive or long-lived software projects

## What is demonstrated internally

- The core knowledge model and its CLI, API, and MCP read workflows are implemented and testable.
- A defined pilot profile can control parallel agent changes through sealed repository/context
  snapshots, explicit write sets, leases, evidence gates, and human promotion decisions.
- A reference scenario and a synthetic load scenario with five separate human principals and five
  agents are automated for both SQLite and PostgreSQL.
- Overlapping write sets, expired or revoked leases, failed gates, and agent-side promotion attempts
  are handled fail-closed in that defined profile.
- The documentation pipeline runs against the maintainer's own architecture corpus — the stack is
  applied to itself, which is where most of its defects are found.
- Local validation covers full-text search, drift analysis, the governed-change cycle, packaging,
  dependency evidence, and isolated recovery/reconciliation.

This is implementation evidence from maintainer-controlled and synthetic environments. It is not a
claim of customer validation, production readiness, ROI, compliance certification, CI green, P0
completion, or universal protection against administrators and direct database access.

## Explore the showcase

- [Why AKDB](WHY_AKDB.md) — why a knowledge layer, and not a wiki or RAG
- [How the approach works](HOW_IT_WORKS.md)
- [Example workflows](workflows/README.md)
- [Example outputs](reports/README.md)
- [Client outcomes](CLIENT_OUTCOMES.md)
- [Status and outlook](STATUS_AND_OUTLOOK.md)

## Services

AKDB and the surrounding tooling are developed and delivered as part of independent software
architecture and AI engineering services. Typical engagements include architecture knowledge
assessments, project onboarding, drift analysis, agent-context integration, governed pilot
preparation, and ongoing architecture knowledge maintenance.

For implementation, integration, or a project-specific assessment, contact the author directly.

## Public disclosure boundary

Everything in this repository is intentionally approved for public disclosure. It contains no trade
secrets, credentials, customer data, commercial terms, pricing, or non-public implementation source.
AKDB and the surrounding tools remain proprietary technology; the descriptive material and synthetic
examples in this showcase do not grant access to the implementation and do not represent customer
projects.

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

**Status date: 10 September 2026.** The tagged AKDB **0.5.0** baseline remains distinct
from active **0.6 development**. The baseline includes project-scoped knowledge,
SysML v2 views, temporal context, governed change, persisted diagnostics and delivery
trace. Newer development extends human-readable application results, source-bound
investigation and compiled application access. Native Xbox work now includes local
knowledge operations, retrieval and recovery, with bounded desktop verification and
separate device evidence. It makes a compact workspace for restricted environments
a more concrete development direction; complete server equivalence remains open.

AKDB remains an engineering preview. Component implementations, authored plans,
synthetic tests and device observations establish different things. No individual
pass qualifies the complete product or every deployment profile. Broader automated
analysis and remedy integration remains development work.

External evaluation, independent security review, repeatable customer delivery and
complete release validation remain explicit gates. No customer effectiveness,
productivity, financial or commercial-success result is claimed. See
[Status and Outlook](STATUS_AND_OUTLOOK.md) for component maturity, evidence limits
and the next evaluation steps.

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
drift and stale-knowledge signals, change-impact analysis, read-only Git evidence, and immutable
project-local SysML v2 commit graphs. PostgreSQL is live authority; SQLite is the verified portable
backup and offline mode. CLI, API, and MCP operate over the same knowledge contracts.

**ContextOps — the control plane.**
Compiles and executes work *from* canonical knowledge while never becoming an alternative authority
for it. Live operational truth is PostgreSQL; jobs, runs, and leases are the execution ledger.
Bounded agent work runs under an external-host protocol: the server does not start agent processes
as children, and hosts pull work through `/agent-hosts/claims` rather than an in-process `/dispatch`.
Hosts register, claim queued work under a lease, heartbeat, emit idempotent events, and complete or
fail explicitly. Around that sit attention and read-tier policies, an append-only ledger, participant
presence and floor coordination, structured team-meeting contracts, and a persisted diagnostic
model that distinguishes observations, findings, verdicts, and the evidence each verdict examined.

**Compiled application access — active development.**
Human-readable results and structured automation access serve different users of
the same knowledge. The native Xbox workspace explores how selected knowledge
functions can run beside locally held data, with packaged software and local
retrieval instead of a separate server for each function. This matters where
project material must stay within a controlled environment and additional
infrastructure is costly to introduce. The scope is qualified function by function;
reduced setup and support effort still needs measurement in an actual deployment.

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
- Human-readable structural, behavioral, requirements, and evidence views through per-project
  SysML v2 and stakeholder projections
- Temporarily bridgeable agent memory bounded by task, plan, module, session, sensitivity, and TTL
- Reviewable change-impact and architecture-review outputs
- A bounded governed-change path with explicit scope, leases, evidence gates, and human approval
- Dated operational diagnostics for environment readiness, host presence, blocked work, evidence
  gates, delivery registers, and derived knowledge
- Trace from an approved plan revision and work package to delivered changes, declared impact, and
  knowledge that may need re-examination
- Local-first operation suitable for sensitive or long-lived software projects

## What is demonstrated internally

- The core knowledge model and its CLI, API, and MCP read workflows are implemented and testable.
- A defined pilot profile can control parallel agent changes through sealed repository/context
  snapshots, explicit write sets, leases, evidence gates, and human promotion decisions.
- A reference scenario and a synthetic load scenario with five separate human principals and five
  agents are automated for both SQLite and PostgreSQL.
- Overlapping write sets, expired or revoked leases, failed gates, and agent-side promotion attempts
  are handled fail-closed in that defined profile.
- Diagnostic runs persist what was examined and treat absent or unverifiable evidence as a finding,
  while eligible findings can prepare reviewable remedy proposals without self-approving them.
- Delivery evidence can be bound to an approved plan revision, work package, impact declaration,
  invalidation footprint, and lineage record.
- The documentation pipeline runs against the maintainer's own architecture corpus — the stack is
  applied to itself, which is where most of its defects are found.
- Existing records for six maintained projects have been reconciled into separate SysML v2 models;
  the models remain separate even where products belong to the same solution family.
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

This showcase is limited to public capability descriptions and synthetic examples. It contains no trade
secrets, credentials, customer data, commercial terms, pricing, or non-public implementation source.
AKDB and the surrounding tools remain proprietary technology; the descriptive material and synthetic
examples in this showcase do not grant access to the implementation and do not represent customer
projects.

Updates to this showcase do not themselves authorize publication of private implementation,
release artifacts or commercial material.

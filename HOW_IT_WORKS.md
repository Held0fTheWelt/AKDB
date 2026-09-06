# How the approach works

AKDB is used as a knowledge and review layer around the sources that remain authoritative in a
project. The tools around it add a control plane, an access model, and an evidence view on top of
that same knowledge — without any of them becoming a second authority for it.

```text
Project sources
    ├── ADRs and architecture documents
    ├── UML, PlantUML, Mermaid, and SysML v2 interchange
    ├── rules, definitions, and structured files
    └── registered repository and Git evidence
              │
              ▼
      Structured architecture knowledge          ← AKDB: the record
              │
      Project-local SysML v2 history              ← human visibility, not a second authority
              │
       ┌──────┴──────────────┬───────────────────┐
       ▼                     ▼                   ▼
   Read and review       Governed change     Evidence view
   ├── Search            ├── Sealed scope    ├── Repository
   ├── Drift             ├── Lease + writes  ├── Agent runs
   ├── Context packs     ├── Evidence gates  ├── Packages
   └── Change impact     └── Human decision  ├── Documents + UML
                                              └── Dated diagnostics
       │                     │                   │
       └──────────┬──────────┴───────────────────┘
                  ▼
         Reviewable engineering work
```

AKDB does not replace the repository, the documentation, or the architecture owner. It relates and
evaluates knowledge so that people and coding agents can use it before a change is made.

## Five principles

- **One record, many artefacts.** Published documents, diagrams, and fact sheets are compiled from a
  single authority rather than maintained in parallel. A derived file is never hand-corrected; the
  export is re-run.
- **Gates fail closed.** A check that cannot prove its property refuses rather than warns. This is
  occasionally inconvenient and is the reason the corpus stays trustworthy.
- **Evidence travels with conclusions.** A report carries the measurement it rests on, so a reader
  can disagree with the conclusion and still trust the number.
- **The human decides.** Automated analysis prepares a change. A person approves it. No agent
  promotes its own work.
- **Projects remain isolated.** Each project owns its PostgreSQL authority and SysML history.
  Products may share a solution family without sharing records, permissions, or commit graphs.

## Typical loop

1. Register the project sources.
2. Build or refresh the architecture knowledge view.
3. Ask for context for a concrete engineering task.
4. Review decisions, constraints, relationships, and drift signals.
5. Make the change in the owning source files.
6. Reconcile the knowledge view after the change.

For long-running work, the context pack can be supplemented by bitemporal memory workspaces scoped
to a task, plan, module, agent, or session. Explicit handoffs bridge selected knowledge temporarily;
TTL, sensitivity, egress policy, and token budget prevent the bridge from becoming an ungoverned
global memory.

## Reviewing a result

A useful result needs both an understandable conclusion and a route back to its
sources. Human-readable application views support that review while structured
interfaces remain available to automation. The reviewer should be able to distinguish
observations, inferred relationships, missing coverage and actions that still need
a decision.

Source-bound navigation and bounded comparisons help investigate a proposed change.
They do not establish universal code understanding or prove that every dependency
has been found. The broader automated analysis-and-remedy workflow remains separate
from these implemented review capabilities.

## Operating profiles

Server and portable application profiles have different scope and qualification.
A local copy or view does not automatically become a second authoritative database.
Current compiled application work extends access to knowledge and local workflows;
integration, authorization and recovery still need qualification for the selected
profile. The [status overview](STATUS_AND_OUTLOOK.md) separates these developments
from completed release claims.

## Governed change loop

For a deliberately bounded agent-assisted change, the reviewed internal pilot profile adds a control
path around the engineering work:

1. Seal the repository baseline and the architecture context used for the task.
2. Bind the task to an approved plan revision and work package where that control is required.
3. Define the permitted project, repository, tools, paths, write set, and intended impact.
4. Issue a bounded lease for non-conflicting work.
5. Collect run events, lineage, invalidation footprint, and required evidence from the change.
6. Evaluate explicit review and validation gates.
7. Require a human decision before the change can enter the promotion state.
8. Preserve the decision, examined evidence, and a linked recovery or rollback path.

Overlapping write sets, expired or revoked leases, missing evidence, failed gates, and agent-side
promotion attempts are rejected in this profile. This is a supervised pilot control model, not a
claim that the system autonomously merges arbitrary Git changes or can prevent a database
administrator from bypassing every application-level control.

## How agents are attached

Agent work is pulled, not pushed. ContextOps live operational truth is PostgreSQL; jobs, runs, and
leases are the execution ledger. The control plane does not start agent processes as children of
itself. An external host registers and claims queued work at `/agent-hosts/claims` under a lease —
not through an in-process `/dispatch` — then heartbeats while it runs, emits idempotent events, and
completes or fails explicitly. Two consequences matter more than the mechanism:

- **A crashed or disappearing agent is a recoverable state**, not a corrupted one. The lease expires
  and the work returns to the queue.
- **The agent's client does not matter.** Access goes through one client-agnostic MCP layer, so
  Claude Code, Codex, Cursor, or any other MCP client reads the same knowledge under the same rules.

Reads are made cheap on purpose, because an agent that cannot afford to look things up will guess
instead. Writes stay expensive, scoped, and reviewable.

## How diagnosis stays evidence-backed

Operational diagnosis is stored as runs, results, findings, and dated observations rather than a
single mutable health flag. Checks can examine environment readiness, agent-host liveness, blocked
jobs, evidence gates, delivery registers, and derived knowledge. A verdict records what it examined;
missing or unverifiable evidence remains visible instead of being converted into a clean result.

Where policy permits it, a finding can prepare a bounded remedy proposal. The proposal does not
approve itself: it retains its authority boundary, expected impact, and evidence for human review
and later re-examination.

## How the pipeline keeps itself honest

The same method is applied to the maintainer's own architecture corpus, which is where most of its
defects surface first. In practice that means:

- exports are compared against the record before they may be committed;
- a sync that would silently remove a generated navigation or depth section is refused;
- cross-references are link-checked, and traceability between decisions, specifications, models, and
  source anchors is measured rather than asserted;
- coverage is reported in both directions — what the documentation claims and what the code actually
  contains — so that a gap shows up as a number instead of a feeling.

Dogfooding is not a virtue signal here. It is the cheapest available source of honest failure cases.

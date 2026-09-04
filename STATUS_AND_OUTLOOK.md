# Status and Outlook

**Status date:** 4 September 2026

**AKDB release line:** `0.5.0`

This document separates what exists today from what still has to be demonstrated. It describes the
work at a public, decision-useful level and contains no trade secrets, credentials, customer data,
commercial terms, or non-public implementation details.

## Component maturity

Maturity differs sharply between the pieces, and the difference is the point of this table. Nothing
below is a shipped promise except where it says so.

| Component | Maturity | What that means |
|---|---|---|
| ArchitecturalKnowledgeDB | Engineering preview, release line `0.5.0` | P0-P13, SysML v2, governed evidence, temporal memory, and persisted diagnostics are implemented; broader production readiness is not claimed |
| ContextOps control plane | Implemented internally, unreleased | PostgreSQL is live operational truth; jobs, runs, and leases are the execution ledger; no external operation, no delivery model |
| Agent Collaboration Plane | Architecture accepted, read layer implemented | Client-agnostic MCP reads work; the wider operating model is partly built |
| Tiny Tool Observatory | Implemented local workbench | Internal maintainer tooling; not offered as a product |
| Documentation pipeline | In continuous internal use | Applied to the maintainer's own corpus daily; the source of most found defects |
| Augmented Operator | Target architecture, **not created** | Reviewed intent with a specified target; no implementation exists |

## Current position

The implementation supports:

- project-scoped architecture knowledge and explicit shared spaces;
- decisions, rules, diagrams, source areas, symbols, definitions, and provenance;
- searchable, task-specific context assembly for people and coding agents;
- drift, stale-knowledge, and change-impact analysis;
- read-only Git evidence and source-anchored outputs;
- PostgreSQL as live operational authority, with verified SQLite backup and offline operation;
- CLI, API, and MCP access;
- DB-native architecture-document and UML authoring with deterministic export;
- a governed pilot profile for bounded, supervised agent changes;
- an external-host protocol under which agent work is claimed by lease at `/agent-hosts/claims`,
  not dispatched in-process at `/dispatch`; and
- append-only revision, observability, recovery, and reproducible package-validation foundations;
- immutable project-isolated SysML v2 histories with deterministic AKDB reconciliation; and
- task-, plan-, module-, agent-, and session-bound bitemporal memory workspaces;
- persisted diagnostic runs, results, findings, and dated observations across environment,
  liveness, jobs, evidence gates, delivery registers, and derived knowledge;
- delivery binding from approved plan revisions and work packages to impact declarations,
  invalidation footprints, lineage, and examined evidence; and
- governed remedy proposals plus a container deployment path for the external Agent Host.

The system remains an engineering preview. Version `0.5.0` identifies one coherent implementation
line; it is not presented as a generally available production service, a completed enterprise
platform, or externally validated customer software.

## P0-P13 foundation and 0.5.0 diagnostic extension

The former wave-by-wave P0 snapshot is retired. The versioned implementation now contains P0-P13:
truth integrity, projections and locators, conformance workflow trace, operation and schema
contracts, governed proposals, cockpit and tenant isolation, distributed recovery, connectors,
evidence lifecycle, multilingual retrieval, bitemporal memory, and stakeholder/SysML visibility.
Version 0.5.0 adds a persisted diagnostic and delivery-trace layer over that foundation. A verdict
records its examination scope; absent evidence remains unverifiable instead of being interpreted as
clean; and a proposed repair remains subject to the same governed authority and human decision path.

Plan-chain references are governed by revision and content hash. SysML history is a separate,
immutable project-local commit graph and does not replace the AKDB plan, evidence, or source
authority. No solution-family label merges independent project databases.

## Evidence boundary

### Demonstrated internally

- the core knowledge model and primary workflows are implemented and testable;
- multiple access surfaces operate over the same architectural knowledge;
- the implementation can ingest, relate, search, review, and export architecture information;
- local-first and self-hosted operating paths are part of the design;
- a defined governed-change profile uses sealed context/repository snapshots, explicit write sets,
  leases, evidence gates, and human promotion decisions;
- overlapping write sets, invalid leases, failed gates, and agent promotion attempts fail closed in
  that profile;
- reference and synthetic five-human/five-agent scenarios are automated for SQLite and PostgreSQL;
- diagnostics record dated observations and isolate individual check failures instead of turning
  one unavailable check into a false whole-system verdict;
- delivered work can retain its approved plan/package binding, declared impact, invalidation
  footprint, and lineage for later re-examination;
- ADR and DB-canonical document changes have append-only revisions, stale-write protection,
  approval references, and revert-as-new-revision;
- the documentation pipeline is exercised continuously against the maintainer's own architecture
  corpus, including its export, drift, link, and traceability gates; and
- local benchmark, packaging, dependency, observability, and isolated recovery evidence exists.

### Still to be demonstrated externally

- useful results on a repository outside the maintainer-controlled test estate;
- independent acceptance of accuracy, completeness, and decision value;
- security and operational review under real customer constraints;
- measured effort, runtime, recovery, and support requirements;
- repeatability across more than one independent project; and
- a validated delivery, partnership, or product model.

Internal test coverage is evidence of implementation quality. It is not evidence of customer need,
production suitability, or commercial traction.

The governed profile does not claim that every mutation by arbitrary processes or database
administrators is technically impossible. It does not perform an autonomous real-world Git merge,
does not make its ledger tamper-proof against administrators, and does not establish productivity,
ROI, high availability, RPO/RTO, multi-tenancy, or compliance certification.

## Current development focus

The active work is release consolidation and external proof, not another internal phase-number
claim.

After that lock lifts, the release path still has to demonstrate the following. These are not a
schedule, not a claim that the work has started, and not shipped promises:

1. **External transferability:** prove decision value on a repository outside the maintainer's test
   estate, beginning read-only or with a narrowly governed write scope.
2. **Release integrity:** validate package, interfaces, supported storage paths, documentation, and
   deployment evidence on one clean revision.
3. **Operational assurance:** complete independent security review, secret and dependency review,
   restore exercises, and realistic operator/support measurements.
4. **Delivery evidence:** define the bounded service or product package, customer responsibilities,
   deletion and rollback terms, and measurable acceptance criteria.
5. **Closing the record:** make every published artefact derivable from the authority, so that no
   part of the documentation survives only because a repair routine knows where to find it.

A capability becomes part of a release only after it is versioned, documented, and validated on the
same revision.

## Release gates

Before a broader release, the stack should demonstrate:

- a clean, reproducible test and package-validation run;
- consistent CLI, API, and MCP startup from a clean installation;
- migration, backup, restore, and reconciliation evidence for supported storage paths;
- fail-closed authority across every supported mutation surface;
- secret-free diagnostics and reviewed dependency, advisory, and distribution status;
- a delivery agreement aligned with the proprietary implementation license and third-party terms;
- a clear separation between local conformance fixtures and production integrations.

## Outlook

The stack addresses a durable problem: teams and coding agents need architecture context that is more
authoritative, traceable, and reviewable than a search result or a prompt-sized document dump. The
credible opportunity is a sovereign context and control layer for complex or sensitive software
systems — one that stays local, keeps its record inspectable, and puts a human at the decision point.

The direction beyond that is stated openly and marked as intent: making operator functions usable
away from a desk, as spatial workflows on a headset, with the device owning its runtimes and local
data rather than mirroring a remote UI. That target architecture is reviewed. It is not built.

The outlook remains deliberately evidence-led:

1. **Complete release proof.** Close the technical, operational, and licensing gates on one clean
   revision.
2. **Run a bounded external pilot.** Start read-only or with a narrowly governed write scope and
   agree access, deletion, review, rollback, and success criteria in advance.
3. **Measure repetition.** Record accuracy, missing context, operator effort, runtime, recovery, and
   decision value across independent cycles.
4. **Choose the operating model.** Decide between a focused expert service, partner-operated
   deployment, or supported product only after external evidence exists.
5. **Scale selectively.** Pursue multi-tenancy, broad integrations, high availability, or team growth
   only when observed demand makes one of them a real constraint.

A smaller dependable deployment is a valid outcome. Platform scale is an option, not the definition
of success.

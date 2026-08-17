# Status and Outlook

**Status date:** 17 August 2026

**AKDB release baseline:** `0.3.0`

This document separates what exists today from what still has to be demonstrated. It describes the
work at a public, decision-useful level and contains no trade secrets, credentials, customer data,
commercial terms, or non-public implementation details.

## Component maturity

Maturity differs sharply between the pieces, and the difference is the point of this table. Nothing
below is a shipped promise except where it says so.

| Component | Maturity | What that means |
|---|---|---|
| ArchitecturalKnowledgeDB | Engineering preview, packaged baseline `0.3.0` | Implemented and testable; later capabilities are versioned internal implementation, not a declared release |
| ContextOps control plane | Implemented internally, unreleased | Runs for the maintainer's own work; no external operation, no delivery model |
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
- SQLite and PostgreSQL storage paths;
- CLI, API, and MCP access;
- DB-native architecture-document and UML authoring with deterministic export;
- a governed pilot profile for bounded, supervised agent changes;
- an external-host protocol under which agent work is claimed by lease rather than spawned; and
- append-only revision, observability, recovery, and reproducible package-validation foundations.

The packaged release remains `0.3.0`; later capabilities are versioned internal implementation and
have not yet been declared a broader release. The system is currently an engineering preview. It is
not presented as a generally available production service, a completed enterprise platform, or
externally validated customer software.

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

Current work concentrates on five connected areas:

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

These are active development areas, not shipped promises. A capability becomes part of a release only
after it is versioned, documented, and validated on the same revision.

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

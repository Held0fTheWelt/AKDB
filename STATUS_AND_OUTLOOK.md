# AKDB Status and Outlook

**Status date:** 6 August 2026

This document separates what exists today from what still has to be demonstrated. It describes the
project at a public, decision-useful level and contains no trade secrets, credentials, customer data,
or non-public implementation details.

## Current position

AKDB has a substantial internal engineering baseline. The implementation supports:

- project-scoped architecture knowledge and explicit shared spaces;
- decisions, rules, diagrams, source areas, symbols, definitions, and provenance;
- searchable, task-specific context assembly for people and coding agents;
- drift, stale-knowledge, and change-impact analysis;
- read-only Git evidence and source-anchored outputs;
- SQLite and PostgreSQL storage paths;
- CLI, API, and MCP access; and
- DB-native architecture-document and UML authoring with deterministic export.

The system is currently an engineering preview. It is not presented as a generally available
production service, a completed enterprise platform, or externally validated customer software.

## Evidence boundary

### Demonstrated internally

- the core knowledge model and primary workflows are implemented and testable;
- multiple access surfaces operate over the same architectural knowledge;
- the implementation can ingest, relate, search, review, and export architecture information;
- local-first and self-hosted operating paths are part of the design; and
- governance, recovery, observability, and release-hardening work has concrete implementation
  behind it.

### Still to be demonstrated externally

- useful results on a repository outside the maintainer-controlled test estate;
- independent acceptance of accuracy, completeness, and decision value;
- security and operational review under real customer constraints;
- measured effort, runtime, recovery, and support requirements;
- repeatability across more than one independent project; and
- a validated delivery, partnership, or product model.

Internal test coverage is evidence of implementation quality. It is not evidence of customer need,
production suitability, or commercial traction.

## Current development focus

Work after the baseline concentrates on four connected areas:

1. **Governed change:** fail-closed write authority, reviewable promotion, revision history,
   rollback links, and bounded agent execution.
2. **Supervised operation:** external agent execution and operator surfaces for controlled,
   observable engineering workflows.
3. **Operational hardening:** PostgreSQL role separation, backup and restore proof, reconciliation,
   observability, secret management, and dependency compliance.
4. **Release integrity:** repeatable package builds, clean-environment installation, interface
   smoke tests, storage-backend parity, and documentation tied to the tested revision.

These are active development areas, not shipped promises. A capability becomes part of a release
only after it is versioned, documented, and validated on the same revision.

## Release gates

Before a broader release, AKDB should demonstrate:

- a clean, reproducible test and package-validation run;
- consistent CLI, API, and MCP startup from a clean installation;
- migration, backup, restore, and reconciliation evidence for supported storage paths;
- fail-closed authority across every supported mutation surface;
- secret-free diagnostics and reviewed dependency, advisory, and distribution status;
- an explicit licensing and delivery model; and
- a clear separation between local conformance fixtures and production integrations.

## Outlook

AKDB addresses a durable problem: teams and coding agents need architecture context that is more
authoritative, traceable, and reviewable than a search result or prompt-sized document dump. Its
credible opportunity is a sovereign context and control layer for complex or sensitive software
systems.

The outlook remains deliberately evidence-led:

1. **Complete release proof.** Close the technical, operational, and licensing gates on one clean
   revision.
2. **Run a bounded external pilot.** Start read-only or with a narrowly governed write scope and
   agree access, deletion, review, rollback, and success criteria in advance.
3. **Measure repetition.** Record accuracy, missing context, operator effort, runtime, recovery,
   and decision value across independent cycles.
4. **Choose the operating model.** Decide between a focused expert service, partner-operated
   deployment, or supported product only after external evidence exists.
5. **Scale selectively.** Pursue multi-tenancy, broad integrations, high availability, or team
   growth only when observed demand makes one of them a real constraint.

A smaller dependable deployment is a valid outcome. Platform scale is an option, not the
definition of success.

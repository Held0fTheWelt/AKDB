# What clients receive

A project-specific evaluation can produce the outputs below. They describe possible
deliverables, not completed customer engagements or guaranteed improvements. Scope
and acceptance depend on the available sources and the operating profile qualified
for the work.

## Understanding an existing system

- a structured view of the project's architectural decisions and constraints;
- source-anchored context packs for recurring engineering tasks;
- a report of stale, contradictory, or disconnected architecture knowledge;
- a change-impact view before a major refactoring or feature, with source coverage
  and uncertain relationships made explicit;
- separate human-readable structural, behavioral, requirements, and evidence views generated from
  a project-local SysML v2 history;
- an onboarding package for engineers joining a complex project; and
- a repeatable workflow for keeping architecture knowledge useful over time.

## Working with coding agents

- a client-agnostic access path, so the team is not locked to one agent product;
- context assembly tuned for a concrete task instead of undifferentiated prompt dumps;
- bounded temporal memory and explicit handoffs across a task, plan, or module without collapsing
  project knowledge bases into one global agent memory;
- explicit scope boundaries: which projects, paths, and tools an agent may touch;
- evidence-backed diagnostic summaries that separate observed facts, findings, and unverifiable
  conditions instead of collapsing them into one health label;
- trace from approved plan and package scope to delivered change, declared impact, and affected
  knowledge;
- a review path where the agent prepares and a human decides; and
- where appropriate, a bounded governed-change pilot with evidence gates, human approval, and a
  documented recovery path.

## Keeping documentation true

- architecture descriptions, diagrams, and fact sheets derived from one authority rather than
  maintained in parallel;
- automated checks that refuse a change which would reduce traceability or silently drop content;
- coverage measured in both directions — what the documentation claims, and what the code contains;
  and
- a defined procedure for the case that matters most: what happens when the record and reality
  disagree.

The exact scope depends on the project's size, source landscape, security requirements, and desired
operating model.

## Evidence delivered with a governed pilot

A governed pilot is framed as an evaluation, not as a production-readiness claim. Its deliverables
can include:

- the agreed repository baseline, architecture-context snapshot, and permitted change scope;
- explicit path/write-set boundaries and review ownership;
- a record of lease, run, evidence, gate, and human-decision events;
- dated diagnostic observations, delivery lineage, and knowledge marked for re-examination;
- human-readable findings with source references, validation scope and unresolved
  architecture questions;
- a linked recovery or rollback procedure; and
- measured operator effort, runtime, missing context, and decision value.

Customer outcomes, productivity effects, and repeatability must be measured in the customer's own
environment; synthetic internal validation cannot establish them in advance.

For teams whose project material must stay inside a controlled environment, native
workspace development opens an additional evaluation question: which knowledge
tasks can be handled locally, with fewer separately operated services? A suitable
case would measure installation and update effort, permitted data movement, review
quality and recovery alongside the task result. The Xbox work supplies a concrete
engineering basis for that question; it does not yet establish suitability for a
particular sensitive environment or lower operating cost.

## What is deliberately not promised

- that an agent can be trusted to merge its own work;
- that a gate can be both strict and never inconvenient;
- that a knowledge layer removes the need for an architecture owner; or
- a productivity, ROI, availability, or compliance figure that has not been measured in the
  environment it is quoted for.

Preparation, review and ongoing knowledge maintenance must be measured separately;
released capacity is not automatically cash savings.

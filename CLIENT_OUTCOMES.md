# What clients receive

Engagements are outcome-oriented. The deliverable is not a database, a server, or an integration; it
is a more reliable way to understand and change a software system, and a record that stays useful
after the engagement ends.

## Understanding an existing system

- a structured view of the project's architectural decisions and constraints;
- source-anchored context packs for recurring engineering tasks;
- a report of stale, contradictory, or disconnected architecture knowledge;
- a change-impact view before a major refactoring or feature;
- an onboarding package for engineers joining a complex project; and
- a repeatable workflow for keeping architecture knowledge useful over time.

## Working with coding agents

- a client-agnostic access path, so the team is not locked to one agent product;
- context assembly tuned for a concrete task instead of undifferentiated prompt dumps;
- explicit scope boundaries: which projects, paths, and tools an agent may touch;
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
- validation results and unresolved architecture questions;
- a linked recovery or rollback procedure; and
- measured operator effort, runtime, missing context, and decision value.

Customer outcomes, productivity effects, and repeatability must be measured in the customer's own
environment; synthetic internal validation cannot establish them in advance.

## What is deliberately not promised

- that an agent can be trusted to merge its own work;
- that a gate can be both strict and never inconvenient;
- that a knowledge layer removes the need for an architecture owner; or
- a productivity, ROI, availability, or compliance figure that has not been measured in the
  environment it is quoted for.

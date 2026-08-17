# Why AKDB exists

RAG can retrieve relevant text. An LLM wiki can synthesize information into an interconnected knowledge base. Both are useful, but software architecture requires additional control.

Architecture knowledge is not just text. It includes:

- decisions and their rationale;
- rules and guardrails;
- diagrams and system relationships;
- definitions and source areas;
- provenance and ownership;
- dependencies and change history; and
- the question of whether a statement is still valid.

AKDB is designed around that distinction. It helps teams move from *relevant information* to
*reviewable architectural context*. Its governed pilot path also addresses a second problem:
parallel AI-assisted changes can exceed the available review and architecture-control capacity even
when the team itself is small.

The core questions are:

1. What is authoritative?
2. What does this decision or rule affect?
3. What evidence supports it?
4. Has the implementation or documentation drifted?
5. What should an engineer or coding agent know before making a change?
6. Who may change which area, using what evidence and review path?
7. What happens when scope overlaps, authority expires, or a gate fails?

The relevant operating pressure is the number and dependency of concurrent changes relative to the
capacity to review and approve them—not a fixed minimum number of developers.

## Why there is tooling around it

A knowledge layer answers *what is true*. It does not by itself answer *who may change what, under
which evidence, and what happens when two changes overlap*. Those are different questions, and
answering them inside the knowledge layer would turn the record into a workflow engine — which is
exactly how records stop being trustworthy.

So the surrounding tools are deliberately separate and deliberately subordinate:

- a **control plane** compiles and executes bounded work *from* the record, and is never allowed to
  become a second authority for it;
- an **access model** keeps agent reads cheap and agent writes scoped, through one client-agnostic
  interface rather than one vendor's;
- an **evidence view** collects what the other tools produced, without claiming to have produced it;
  and
- a **documentation pipeline** compiles published artefacts from the record, so that a document can
  never quietly become the newer truth.

Each is useful without the others. None of them is allowed to overrule the record. That constraint
is what makes the record worth keeping.


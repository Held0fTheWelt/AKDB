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

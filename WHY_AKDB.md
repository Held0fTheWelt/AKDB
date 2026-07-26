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

AKDB is designed around that distinction. It helps teams move from *relevant information* to *reviewable architectural context*.

The core questions are:

1. What is authoritative?
2. What does this decision or rule affect?
3. What evidence supports it?
4. Has the implementation or documentation drifted?
5. What should an engineer or coding agent know before making a change?

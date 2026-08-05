---
name: methodology_documentation_effort_ceiling
description: "Don't spend more time documenting than doing — documentation can be dead on arrival. Bounds how eagerly to propose new doc-based conventions."
metadata: 
  node_type: memory
  type: feedback
  originSessionId: 9c6b45a7-a253-4f6b-a0fa-ac50bd7f8c3d
  modified: 2026-08-05T15:57:36.405Z
---

Don't let documentation effort exceed the effort of the work it describes. A doc can be written and never read or kept current — pure waste. This bounds new doc-based conventions: git-native durability winning over GitHub lock-in isn't enough by itself; it has to clear "will this actually get used," not just "is it more portable in principle."

**Why:** Stated directly 2026-08-05, mid-discussion on whether to add a `docs/ticket-planning` convention on top of the investigations one added the same session.

**How to apply:** Before proposing a new doc type/folder, check if the lightest mechanism already covers it — e.g. propose-in-chat-then-create (used for #151's ADR ticket) instead of a new PR-reviewed doc convention. Reach for a durable doc only once the lighter version is shown to not be enough, the way investigations was — SpendfulnessCli's version had already been used, not just proposed.

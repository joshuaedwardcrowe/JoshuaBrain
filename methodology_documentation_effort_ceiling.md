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

**Restating a rule you broke does not enforce it.** When work violates a convention that was already written down, the failure was reading it, not wording it — and adding words to the same doc changes nothing about whether it gets read next time. Revert the addition, say plainly that the existing rule already covered it, and if the miss is worth preventing, propose a *mechanism* (a CI check, a template field) rather than more prose. Only add wording when the rule genuinely was not there.

**Why:** caught 2026-08-25 on KitCli #151. CONTRIBUTING said every PR "gets a line in CHANGELOG.md"; I wrote a thirty-line entry, then, when told changelogs should be plain-language, added a six-line tone rule to that same section — including an audience fact ("the `[Unreleased]` notes become the GitHub Release body") already stated twenty lines below it. The user's objection: more wording will not protect against a doc I did not read in the first place.

**How to apply:** Before proposing a new doc type/folder, check if the lightest mechanism already covers it — e.g. propose-in-chat-then-create (used for #151's ADR ticket) instead of a new PR-reviewed doc convention. Reach for a durable doc only once the lighter version is shown to not be enough, the way investigations was — SpendfulnessCli's version had already been used, not just proposed.

---
name: feedback_default_to_brevity
description: "Default to the fewest words that make the point — but dense is not clear: cut words, never the connective tissue that makes a claim followable"
metadata: 
  node_type: memory
  type: feedback
  originSessionId: 9c6b45a7-a253-4f6b-a0fa-ac50bd7f8c3d
  modified: 2026-08-25T19:55:00.000Z
---

Default to the fewest words that make the point, everywhere — replies, doc edits, code comments, memory files. Don't restate context already established nearby. Don't write paragraphs justifying a small edit. If something's flagged as too long, cut it — don't rephrase-and-shorten and repeat the mistake at a smaller scale.

Applies with extra force inside CAIRN/SoloCAIRN docs specifically: they're already terse (short declarative sentences, no re-explaining what a nearby paragraph covers), so match the surrounding line's length before adding anything.

**Why:** Recurred all session 2026-08-05 — three rewrites of one SoloCAIRN line ([PR#21](https://github.com/joshuaedwardcrowe/SoloCAIRN/pull/21)), a paragraph justifying each one. Named directly: "you literally do this everywhere all the time." Recurred again same session, verbatim-copying a 5-paragraph CONTRIBUTING.md section into three repos without checking it against this rule first: "4 paragraphs is war and peace."

**Dense is not clear, and this rule can be over-applied into unreadable.** Cutting words is right; cutting the connective tissue that makes a claim followable is not. A page of terse assertions with every explanation removed is shorter and worse — flagged 2026-08-25 on KitCli investigation 0003, where applying Strunk plus this rule produced something "overwhelmingly difficult to read" and needing "laymen's terms". Explain the problem before asserting things about it, and say why a fact matters, not only that it's true. The target is the fewest words that still land, and an unreadable page lands nothing.

Same failure in conversation: opening with process archaeology — what a doc says, what precedent exists, what the four homes imply — before naming the concrete thing being decided. "I dont understand" (2026-08-25) followed three layered paragraphs where a four-row table of issue → action → why would have done it. Lead with the decision; put the reasoning under it.

**How to apply:** Before sending anything, ask if it's the shortest version that still lands. First fix for "too long" is deletion, not a better sentence. Hard cap given 2026-08-05: chat replies ~2 sentences unless the user asks for more (e.g. explicit option lists) — "why do you write in war and peace."

---
name: feedback_default_to_brevity
description: "Default to the fewest words that make the point — but dense is not clear: cut words, never the connective tissue that makes a claim followable"
metadata: 
  node_type: memory
  type: feedback
  originSessionId: 9c6b45a7-a253-4f6b-a0fa-ac50bd7f8c3d
  modified: 2026-08-26T00:00:00.000Z
---

Default to the fewest words that make the point, everywhere — replies, doc edits, code comments, memory files. Don't restate context already established nearby. Don't write paragraphs justifying a small edit. If something's flagged as too long, cut it — don't rephrase-and-shorten and repeat the mistake at a smaller scale.

Applies with extra force inside CAIRN/SoloCAIRN docs specifically: they're already terse (short declarative sentences, no re-explaining what a nearby paragraph covers), so match the surrounding line's length before adding anything.

**Why:** Recurred all session 2026-08-05 — three rewrites of one SoloCAIRN line ([PR#21](https://github.com/joshuaedwardcrowe/SoloCAIRN/pull/21)), a paragraph justifying each one. Named directly: "you literally do this everywhere all the time." Recurred again same session, verbatim-copying a 5-paragraph CONTRIBUTING.md section into three repos without checking it against this rule first: "4 paragraphs is war and peace."

**Dense is not clear, and this rule can be over-applied into unreadable.** Cutting words is right; cutting the connective tissue that makes a claim followable is not. A page of terse assertions with every explanation removed is shorter and worse — flagged 2026-08-25 on KitCli investigation 0003, where applying Strunk plus this rule produced something "overwhelmingly difficult to read" and needing "laymen's terms". Explain the problem before asserting things about it, and say why a fact matters, not only that it's true. The target is the fewest words that still land, and an unreadable page lands nothing.

Answering a question is the same discipline: state the cause in one line and stop. When the user restates the question, narrows it, or offers their own summary, confirm or correct the one missing piece — don't re-derive the mechanism from the top, with fresh code and file references, every time they probe. Flagged 2026-08-26 on KitCli #182: four exchanges of state-machine explanation to arrive at "that transition isn't in the table", each turn answering as if from scratch. Detail is what the follow-up question is for.

Same failure in conversation: opening with process archaeology — what a doc says, what precedent exists, what the four homes imply — before naming the concrete thing being decided. "I dont understand" (2026-08-25) followed three layered paragraphs where a four-row table of issue → action → why would have done it. Lead with the decision; put the reasoning under it.

**Recurred a fourth time on 2026-08-25** — a thirty-line CHANGELOG entry where `CONTRIBUTING.md` said "a line", hours after the investigation-0003 flag above. The fix was not more wording: this guidance lives in a file that is only loaded as a one-line summary in `MEMORY.md`, so it is not in context at the moment of writing. It is now also a path-scoped rule at `~/.claude/rules/writing-markdown.md` (`paths: **/*.md`), which loads automatically whenever a markdown file is touched, in any repo. That rule states the styles themselves rather than pointing at an exemplar repo, and covers every doc kind — README, user guide, concept, investigation, reference entry — not just ADRs. Confirmed 2026-08-25: Strunk, laymen's terms, a fixed section skeleton per `docs/` folder, and under 60 lines per doc whatever the kind. The rule's content is drawn from what five CONTRIBUTING.md files already agree on (KitCli, SpendfulnessCli, YnabSharp, SoloCAIRN, DataTool.Cli) — ADR vs concept vs investigation vs user guide, when to skip an ADR, verify every name and transcript against source, keep docs current in the same PR. Each repo's own CONTRIBUTING stays binding and more specific; the rule exists because it is loaded at write time and CONTRIBUTING is not. KitCli's 118-178 line ADRs are off-style, not the benchmark. Keep the two in step; this file stays the full reasoning.

**How to apply:** Before sending anything, ask if it's the shortest version that still lands. A diagnostic question gets one sentence; expand only when asked. First fix for "too long" is deletion, not a better sentence. Hard cap given 2026-08-05: chat replies ~2 sentences unless the user asks for more (e.g. explicit option lists) — "why do you write in war and peace."

---
name: methodology-post-plan-to-issue
description: "Post the implementation plan as a GitHub issue comment before starting work, across every repo"
metadata: 
  node_type: memory
  type: feedback
  originSessionId: b5cf6d3c-d35d-4190-8305-f26d1512b390
  modified: 2026-07-31T22:02:41.717Z
---

Once a plan for an issue's implementation is finalized (post-plan-mode, before writing code), post it as a comment on the linked GitHub issue.

**Why:** Keeps the plan reviewable in the same place as the rest of the ticket's history, rather than living only in a chat session. This is a personal working-with-Claude convention, not a project-facing rule for other contributors — so it belongs in memory, not in any repo's CONTRIBUTING.md or in [[methodology_four_homes_framework]]'s SoloCAIRN tier.

**How to apply:** Applies across every repo, any time plan mode produces a plan tied to a specific issue. Prefix the comment `🤖 **Claude:**` per each repo's own standing rule for `gh`-posted comments (the human's account posts it, so it must read as Claude's voice, not theirs). Post after the plan is approved (ExitPlanMode accepted), before the first commit.

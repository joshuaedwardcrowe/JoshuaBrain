---
name: methodology-pr-mirrors-issue-metadata
description: "PRs should carry the same labels and milestone as their linked issue, applied per-repo — not a SoloCAIRN rule"
metadata: 
  node_type: memory
  type: feedback
  subtype: methodology
  originSessionId: 8ca57252-6b27-4f26-9743-8937583c0505
  modified: 2026-07-30T21:16:30.047Z
---

When a PR implements a specific issue, mirror that issue's labels and milestone onto the PR itself. GitHub doesn't do this automatically (confirmed via web search — there's an open GitHub feature request for native inheritance, currently requires manual work or a bot). Apply across every repo, [[methodology_pr_size_limit]]-style — a personal habit replicated into each repo's own `CONTRIBUTING.md`/`CLAUDE.md`, not a shared upstream rule.

**Why:** Learned 2026-07-30 on YnabSharp — merged PR #109 with empty labels/no milestone despite its issue (#79) carrying `feature`/`area:client`/`sev:low` and the `YNAB API v1.86.0` milestone. Checked history: every prior merged PR in that repo had the same gap, so it wasn't a one-off. First instinct was to push the fix into SoloCAIRN so it'd apply everywhere at once — the user caught that this repeats a mistake SoloCAIRN's own docs warn against: [[methodology_four_homes_framework]]'s test says a binding per-repo contributor rule belongs in that repo's `CONTRIBUTING.md`, and `10-what-cairn-does-not-solve.md` explicitly disclaims "conventions and standards" as out of SoloCAIRN's scope (it's scoped to the feature-build artifact pipeline — problem statement → scope → architecture → stories → code — not general repo hygiene).

**How to apply:** When opening or reviewing a PR anywhere, check whether its linked issue has labels/milestone and copy them onto the PR (`gh pr edit --add-label ... --milestone ...`). When touched, add the equivalent line to that repo's own `CONTRIBUTING.md` (see YnabSharp's "Branching & PRs" section for the wording used there) — don't route it through SoloCAIRN or a shared doc, even though the underlying habit is the same everywhere.

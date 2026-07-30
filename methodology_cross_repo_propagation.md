---
name: methodology-cross-repo-propagation
description: "Once a convention is confirmed to span multiple repos, apply it to every one of them in the same sitting - don't stop after the repo that triggered it"
metadata: 
  node_type: memory
  type: feedback
  subtype: methodology
  originSessionId: 8ca57252-6b27-4f26-9743-8937583c0505
  modified: 2026-07-30T22:02:22.713Z
---

Landing a cross-repo convention correctly in JoshuaBrain (the canonical source, per [[methodology_four_homes_framework]]'s "canonical-in-JoshuaBrain + per-repo-copy" shape) is not the finish line. The moment it's confirmed to apply to more than one repo, go apply the matching edit to every repo it governs in the same sitting — don't leave the other repos for a later ask.

**Why:** Verified via git history (2026-07-30) rather than assumed: YnabSharp, SpendfulnessCli, and KitCli's `CONTRIBUTING.md` files were kept in lockstep for nine consecutive shared conventions over two days — commits landing within seconds to minutes of each other across all three repos, every time (e.g. "document Projects convention," "PR size limit, testing conventions," "milestone naming convention"). This was sustained manual discipline, not tooling. It broke exactly once: [[methodology_pr_mirrors_issue_metadata]] and a Status-gates addition landed only on YnabSharp — triggered by a YnabSharp-specific incident (issue #79 sitting stale) — and sat unpropagated until the user had to ask "are these also supposed to be identical across repos" before the gap even surfaced. Nothing caught it automatically; the two-day streak of matching commits just quietly stopped.

This is a distinct failure mode from [[methodology_four_homes_framework]]'s placement mistakes — the *home* was identified correctly (JoshuaBrain, applied per-repo), but the *propagation* across every repo that home implies wasn't completed. Getting the placement right doesn't mean the job is done.

**How to apply:** After adding or editing a cross-repo convention in any one repo's `CONTRIBUTING.md`/`CLAUDE.md`, immediately check every other repo that shares it (cross-reference against existing `methodology_*` memories, or diff `CONTRIBUTING.md` structure across the sibling repos) and apply the matching edit before considering the task done — even if the triggering incident only touched one repo. Don't wait for the user to notice the others are missing it.

---
name: methodology-engineering-estimation-pipeline
description: "The seven-step, deliberately Agile pipeline used before and during any new project — non-binding WAG/SWAG, rolling-wave inception spike, just-in-time backlog refinement, fixed iterations with inspect-and-adapt, then Estimates"
metadata: 
  node_type: memory
  type: feedback
  subtype: methodology
  originSessionId: 681f9a31-eb28-4ccf-8913-2eb0f7bd2929
  modified: 2026-08-05T10:58:34.444Z
---

Before and during committing to build something, work runs through seven steps, documented in KitCli/YnabSharp/SpendfulnessCli's `CONTRIBUTING.md` Projects sections:

1. **WAG** (Wild-Ass Guess) — a fast, rough gut-feel estimate (months), logged on that repo's own Ideas board `WAG (months)` field (see [[methodology_idea_board_layout]] for which board — per-repo by default, the shared board only for ideas that don't pertain to one repo). **Non-binding — expected to be wrong**, purely to judge whether an idea is worth pursuing at all.
2. **SWAG** — the same estimate, re-checked against everything else competing for the slot, logged in the board's `SWAG (months)` field. **Setting `Priority` (`High`/`Medium`/`Low`) is mandatory at this point — Status can't move to `SWAG'd / Prioritized` until it's set**, forcing an explicit call on how the idea stacks up against what's already prioritized (added 2026-08-05, YnabSharp#151 — see [[methodology_four_homes_framework]] for why this rule lives here and per-repo, not in CAIRN/SoloCAIRN: SoloCAIRN's own scope doc names prioritization as explicitly out of its scope). Otherwise non-binding — a relative sizing input for prioritization, not a plan. Prioritizing = sorting/grouping the board by `Priority` or `SWAG`, deliberately no separate roadmap artifact.
3. **New GitHub Project** — once an idea is greenlit, it graduates off the Ideas board into its own project.
4. **Inception spike** — plans only the *next* milestone in real detail; everything beyond is a rough forecast, re-planned properly once actually reached (rolling-wave planning, not a full plan for the whole estimate up front). Refreshes the Ideas board's `Validated Estimate (months)` field as it's learned, not just once.
5. **Backlog refinement, just-in-time** — only the next handful of tickets need full order + estimates at any moment; the rest of a milestone stays a loosely-ordered backlog, refined incrementally. A milestone-scale re-planning pass (formerly called a "milestone spike") is still useful when picking up a milestone cold, but its output is a starting point, not a fixed contract.
6. **Fixed-length iterations + end-of-iteration review** — the inspect-and-adapt loop: check what got done vs. planned, re-prioritize the backlog, feed actual pace back into WAG/SWAG calibration. This is what makes the whole pipeline Agile rather than a Waterfall-style plan nobody revisits.
7. **Tickets with Estimates** — leaf/actionable tickets pulled into an iteration get the Fibonacci `Estimate` field — see [[project_spendfulnesscli_issue_tracking]]. **A point captures effort, complexity, and risk *together*, not duration and not scope-breadth alone** — canonical wording in SoloCAIRN's `docs/03-lifecycle.md` "Sizing" section (also proposed upstream as [CAIRN#1](https://github.com/SiddiqueAbdullah/cairn/pull/1), open since 2026-07-29, so upstream CAIRN itself still sizes only in time). Novelty counts: work with no precedent in the codebase to copy carries real risk and that belongs *in* the number, not set aside from it. The `Estimate`'s value is the Maintainer's to set — see [[methodology_traditional_project_board_layout]] for the propose-vs-assign split.

This process is deliberately Agile, not just Agile-flavored terminology — the earlier version (a single upfront estimate treated as a commitment, one big spike proving a whole milestone's order before starting) was Waterfall/stage-gate shaped despite the vocabulary. The four fixes that make it genuinely Agile: non-binding estimates, rolling-wave planning, just-in-time backlog refinement, and the added inspect-and-adapt iteration step.

**How to apply:** Don't treat a WAG, SWAG, or inception-spike estimate as a commitment — they're inputs to prioritization, expected to be revised. Don't plan a whole milestone's ticket order in one big spike; only the next few tickets need full ordering at any time. Always include the end-of-iteration inspect-and-adapt step when describing or executing this process — it's the part that makes the difference between this being Agile and being Waterfall with Agile vocabulary borrowed on top. See [[feedback_subissue_chronological_order]] for how ordering gets planned jointly rather than solo.

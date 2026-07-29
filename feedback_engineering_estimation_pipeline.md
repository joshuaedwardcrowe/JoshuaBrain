---
name: feedback-engineering-estimation-pipeline
description: "The seven-step, deliberately Agile pipeline used before and during any new project — non-binding WAG/SWAG, rolling-wave inception spike, just-in-time backlog refinement, fixed iterations with inspect-and-adapt, then Estimates"
metadata: 
  node_type: memory
  type: feedback
  originSessionId: 681f9a31-eb28-4ccf-8913-2eb0f7bd2929
  modified: 2026-07-29T05:21:32.947Z
---

Before and during committing to build something, the user's process runs through seven steps, documented in KitCli/YnabSharp/SpendfulnessCli's `CONTRIBUTING.md` Projects sections (rewritten 2026-07-29 to be genuinely Agile, not just Agile-flavored terminology):

1. **WAG** (Wild-Ass Guess) — a fast, rough gut-feel estimate (months), logged on the shared [Ideas board](https://github.com/users/joshuaedwardcrowe/projects/10)'s `WAG (months)` field. **Non-binding — expected to be wrong**, purely to judge whether an idea is worth pursuing at all.
2. **SWAG** — the same estimate, re-checked against everything else competing for the slot, logged in the board's `SWAG (months)` field. Also non-binding — a relative sizing input for prioritization, not a plan. Prioritizing = sorting/grouping the board by `Priority` (`High`/`Medium`/`Low`) or `SWAG`, deliberately no separate roadmap artifact.
3. **New GitHub Project** — once an idea is greenlit, it graduates off the Ideas board into its own project.
4. **Inception spike** — plans only the *next* milestone in real detail; everything beyond is a rough forecast, re-planned properly once actually reached (rolling-wave planning, not a full plan for the whole estimate up front). Refreshes the Ideas board's `Validated Estimate (months)` field as it's learned, not just once.
5. **Backlog refinement, just-in-time** — only the next handful of tickets need full order + estimates at any moment; the rest of a milestone stays a loosely-ordered backlog, refined incrementally. A milestone-scale re-planning pass (formerly called a "milestone spike") is still useful when picking up a milestone cold, but its output is a starting point, not a fixed contract.
6. **Fixed-length iterations + end-of-iteration review** — the inspect-and-adapt loop: check what got done vs. planned, re-prioritize the backlog, feed actual pace back into WAG/SWAG calibration. This is what makes the whole pipeline Agile rather than a Waterfall-style plan nobody revisits.
7. **Tickets with Estimates** — leaf/actionable tickets pulled into an iteration get the Fibonacci `Estimate` field — see [[project_spendfulnesscli_issue_tracking]].

**Why:** The user first stated the process (2026-07-28) as "ultimately, when we engineer, we do it this way," then explicitly asked (2026-07-29) whether it represented traditional Agile delivery. It didn't — WAG/SWAG committing to a validated multi-month estimate up front, and a single spike proving a whole milestone's order before starting, are both Waterfall/stage-gate shaped, not Agile. The user then asked how to make it genuinely Agile and had the four fixes (non-binding estimates, rolling-wave planning, just-in-time backlog refinement, added inspect-and-adapt iterations) written into all three repos' `CONTRIBUTING.md`.

**How to apply:** Don't treat a WAG, SWAG, or inception-spike estimate as a commitment — they're inputs to prioritization, expected to be revised. Don't plan a whole milestone's ticket order in one big spike; only the next few tickets need full ordering at any time. Always include the end-of-iteration inspect-and-adapt step when describing or executing this process — it's the part that makes the difference between this being Agile and being Waterfall with Agile vocabulary borrowed on top. See [[feedback_subissue_chronological_order]] (may need a light update to reflect "backlog refinement" replacing "milestone spike" as the primary mechanism).

---
name: methodology_idea_board_layout
description: "Every repo gets its own Ideas board by default (Status/Priority/WAG/SWAG/Validated Estimate layout); a separate shared board is only for ideas that don't pertain to one repo"
metadata: 
  node_type: memory
  type: feedback
  subtype: methodology
  modified: 2026-08-05T10:58:53.302Z
  originSessionId: 37ed054a-fbd2-48ae-b6fa-8935b7b9001a
---

Every repo gets its own Ideas board for unshaped ideas tied to its current functionality. A separate shared board — [Ideas](https://github.com/users/joshuaedwardcrowe/projects/10), personal account — exists only for ideas that don't pertain to any single repo (e.g. a Claude↔YNAB connector that could live in YnabSharp, become its own repo, or span repos entirely — see YnabSharp#151, the board's current sole occupant).

Current boards: [SpendfulnessCli Ideas](https://github.com/users/joshuaedwardcrowe/projects/13), [YnabSharp Ideas](https://github.com/users/joshuaedwardcrowe/projects/14), [KitCli Ideas](https://github.com/orgs/KitCli/projects/1) (org-owned — KitCli/Diagnosea already had their own board each before this convention was generalized to every repo). JoshuaBrain doesn't have one yet as of 2026-08-05 — create one the same way once it has its first idea-stage item. **SoloCAIRN has no board at all** — it's a docs-only methodology repo with no effort to estimate; its idea-stage issues get worked through directly (open a PR, debate the methodology nuance, merge if unilateral), never staged through WAG/SWAG.

Every board that does exist (per-repo or shared) uses the identical field layout:
- **Status** (single-select) — the pipeline stages a card passes through *while still on this board*: `New (pre-WAG) → WAG'd → SWAG'd / Prioritized → Released`. "Released" means the idea has graduated off this board into its own GitHub Project (step 3 of [[methodology_engineering_estimation_pipeline]]) — it does not mean shipped/deployed. Moving to `SWAG'd / Prioritized` requires `Priority` to already be set — see [[methodology_engineering_estimation_pipeline]]'s SWAG step.
- **Priority** (single-select): `High / Medium / Low`
- **WAG (months)** + **WAG Date** — logged once a rough gut-feel estimate exists
- **SWAG (months)** + **SWAG Date** — logged once re-checked against everything else competing for a slot on *that same board*
- **Validated Estimate (months)** + **Validated Date** — refreshed as the inception spike (post-graduation) learns more

**Why per-repo by default:** corrected 2026-08-05 (YnabSharp#151) from an earlier model where one shared board held every personal-account repo's ideas together. That caused exactly the kind of context loss the pipeline exists to prevent — a repo's idea-stage issues were scattered across a board mixed with unrelated repos', with no way to tell at a glance what pertained to what. The shared board's job shrank to just the genuinely repo-agnostic ideas; everything else moved to its own repo's board (see [[methodology_cross_repo_propagation]] — done in one sitting across SpendfulnessCli, YnabSharp, and the shared board itself, not just the repo that triggered it).

**Technical vs. user-value ideas:** no dedicated "type" field on any of these boards — that distinction lives entirely in whichever labels the underlying issue carries from its own repo's taxonomy, not a board-level property. E.g. SpendfulnessCli#193/#194 are `User Value`, SpendfulnessCli#195 ("No docs/ folder") is `Tech Debt`+`Documentation` with no `User Value` label, and YnabSharp#113 ("revisit client request paths") is `tech-debt`/`area:client`/`sev:low`. Apply whatever labels the source repo's own taxonomy would normally use.

**How to apply:** When creating a new idea for a repo, check whether that repo already has its own Ideas board before defaulting to the shared one. Only use the shared board if the idea genuinely doesn't belong to one repo. See [[feedback_idea_routing]] for the routing decision itself, [[methodology_four_homes_framework]] for how this fits the broader "where does X live" test.

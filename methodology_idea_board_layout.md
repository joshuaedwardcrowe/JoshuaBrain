---
name: methodology_idea_board_layout
description: "Ideas board (Project #10) layout — Status tracks WAG/SWAG pipeline stages by name instead of generic Todo/In Progress/Done, plus Priority and paired estimate/date fields"
metadata: 
  node_type: memory
  type: feedback
  subtype: methodology
  originSessionId: f401e5ac-4951-45c1-93a4-68d32a637226
  modified: 2026-07-30T20:42:04.202Z
---

The shared [Ideas board](https://github.com/users/joshuaedwardcrowe/projects/10) (WAG/SWAG staging for personal-account repos — SpendfulnessCli, YnabSharp, SoloCAIRN, JoshuaBrain; org-owned repos like KitCli/Diagnosea get their own) uses this layout:

- **Status** (single-select) — renamed 2026-07-30 from generic `Todo/In Progress/Done` to name the actual pipeline stages a card passes through *while still on this board*: `New (pre-WAG) → WAG'd → SWAG'd / Prioritized → Released`. "Released" means the idea has graduated off this board into its own GitHub Project (step 3 of [[methodology_engineering_estimation_pipeline]]) — it does not mean shipped/deployed.
- **Priority** (single-select): `High / Medium / Low`
- **WAG (months)** + **WAG Date** — logged once a rough gut-feel estimate exists
- **SWAG (months)** + **SWAG Date** — logged once re-checked against everything else competing for a slot
- **Validated Estimate (months)** + **Validated Date** — refreshed as the inception spike (post-graduation) learns more

**Why:** The board previously used generic Kanban labels that didn't say anything about *where in the WAG→SWAG→graduate pipeline* a card actually sat — you had to cross-reference the WAG/SWAG date fields to tell. Naming Status after the real stages makes the board self-documenting. This does not contradict the CONTRIBUTING.md rule that there's "no separate roadmap artifact" — it's the same single board, just with clearer Status labels, not a second board.

**How to apply:** New ideas start at `New (pre-WAG)`. Move to `WAG'd` once `WAG (months)` is logged, `SWAG'd / Prioritized` once `SWAG (months)` is logged, `Released` once the idea graduates into its own Project (at which point that new project uses [[methodology_traditional_project_board_layout]] instead). "Prioritizing" is still done by sorting/grouping the board by `Priority` or `SWAG` — Status alone doesn't replace that.

**Technical vs. user-value ideas:** the board has no dedicated "type" field — that distinction lives entirely in whichever labels the underlying issue carries from its own repo, not a board-level property. Confirmed mixed on the board already: SpendfulnessCli#193/#194 are `User Value`, but #195 ("No docs/ folder") is `Tech Debt`+`Documentation` with no `User Value` label at all. So a purely technical/architectural idea (e.g. YnabSharp#113, "revisit how client request paths are architected," labeled `tech-debt`/`area:client`/`sev:low`) is not a misuse of this board — apply whatever labels the source repo's own taxonomy would normally use, don't force a `User Value` label onto something that isn't.

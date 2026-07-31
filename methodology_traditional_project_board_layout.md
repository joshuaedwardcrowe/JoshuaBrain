---
name: methodology_traditional_project_board_layout
description: "Standard GitHub Project layout for delivery boards once an idea graduates off the Ideas board — 7-stage Status pipeline, Estimate, Priority"
metadata: 
  node_type: memory
  type: feedback
  subtype: methodology
  originSessionId: f401e5ac-4951-45c1-93a4-68d32a637226
  modified: 2026-07-31T22:49:18.808Z
---

Once an idea graduates off the [Ideas board](https://github.com/users/joshuaedwardcrowe/projects/10) into its own GitHub Project (step 3 of [[methodology_engineering_estimation_pipeline]]), that delivery board follows a standard layout, confirmed 2026-07-30 against Spendfulness (#9), YnabSharp API Coverage (#11), and YNAB Analysis & Automation (#8):

- **Status** (single-select, 7 stages): `Backlog → To Do → In Development → In Review → In QA → Ready for Release → Done`
- **Estimate**: Fibonacci points per ticket, per [[project_spendfulnesscli_issue_tracking]]
- **Priority** (single-select): `High / Medium / Low`

**Why:** #8 (YNAB Analysis & Automation) currently uses `P0/P1/P2` instead of `High/Medium/Low` — an inconsistency, not an intentional variant. `High/Medium/Low` was chosen as the standard because it matches both #9 and #11, and also matches the Priority field already used on the Ideas board itself, so the vocabulary is consistent from WAG stage through delivery.

**How to apply:** New delivery boards should be created with this layout from the start. #8 should be reconciled to `High/Medium/Low` when next touched (not urgent enough alone to warrant a one-off migration pass). Milestones on these boards are named per [[feedback_milestone_naming_convention]].

**These are gates, not just column labels — move the card at each transition as the real work happens, or the board goes stale silently.** Generic triggers (a specific repo's `CONTRIBUTING.md` should translate these into its own conventions, e.g. YnabSharp's version references its PR-label-mirroring rule): `Backlog`→`To Do` on pulling into an iteration + setting `Estimate`; →`In Development` on first commit/branch; →`In Review` on opening the PR; →`In QA` once review threads are resolved and CI is green; →`Done` on merge (the default landing spot — `Ready for Release` is only for a deliberate hold, e.g. a batched release, not a mandatory stop).

**Why this second part matters:** caught 2026-07-30 on YnabSharp#79/PR#109 — the pipeline was already defined and had been followed correctly on every other closed issue on project #11, but #79 sat at `Backlog` through the entire build/review/merge cycle because nothing moved the field as the work actually progressed. Defining a gate structure once is not the same as enforcing it live; audit for staleness after any big merge, don't assume past discipline on other tickets means it happened on this one.

**`In QA` (and any later gate) may only be moved by a human, never by the agent that implemented the work — this is a hard exception to "move the card at each transition."** `In Review`→`In QA`'s stated criteria ("review threads resolved and CI is green") describe when the gate is *ready to be crossed*, not who's allowed to cross it. Everything up through `In Review` is mechanical and safe for the agent to move on its own (a commit exists, a PR exists). `In QA` asserts a human verified the work — an agent moving that field is self-attestation via a board field instead of a PR-approve button, functionally identical to "AI approves its own PR." When the agent's own verification (a spec check, a test run) is the only verification that's happened, it stops at `In Review`, attaches that verification as a reviewable artifact (PR comment, not just chat), and asks the human to check it and move the card themselves.

**Why:** caught 2026-07-31/08-01 on YnabSharp#80/PR#117 — I ran a DTO-vs-spec check, judged it a pass, and moved #80 to `In QA` myself, based on this memory's literal instruction to keep moving the card as gates are met. The user objected ("marked your own homework"). SoloCAIRN's own `skills/qa.md` already names "Letting AI sign off" as an anti-pattern and `03-lifecycle.md` says approval/verification are human decisions — but both are written around PR approval specifically, so the principle didn't fire when the sign-off took the shape of a board-field move instead. Filed [SoloCAIRN#18](https://github.com/joshuaedwardcrowe/SoloCAIRN/issues/18) to extend that public guidance to name status-transitions explicitly; this memory is the corresponding fix on the personal-instruction side, since the public doc being incomplete doesn't excuse this memory from also being incomplete.

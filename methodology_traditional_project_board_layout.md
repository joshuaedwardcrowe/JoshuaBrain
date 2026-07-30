---
name: methodology_traditional_project_board_layout
description: "Standard GitHub Project layout for delivery boards once an idea graduates off the Ideas board — 7-stage Status pipeline, Estimate, Priority"
metadata: 
  node_type: memory
  type: feedback
  subtype: methodology
  originSessionId: f401e5ac-4951-45c1-93a4-68d32a637226
  modified: 2026-07-30T06:18:04.930Z
---

Once an idea graduates off the [Ideas board](https://github.com/users/joshuaedwardcrowe/projects/10) into its own GitHub Project (step 3 of [[methodology_engineering_estimation_pipeline]]), that delivery board follows a standard layout, confirmed 2026-07-30 against Spendfulness (#9), YnabSharp API Coverage (#11), and YNAB Analysis & Automation (#8):

- **Status** (single-select, 7 stages): `Backlog → To Do → In Development → In Review → In QA → Ready for Release → Done`
- **Estimate**: Fibonacci points per ticket, per [[project_spendfulnesscli_issue_tracking]]
- **Priority** (single-select): `High / Medium / Low`

**Why:** #8 (YNAB Analysis & Automation) currently uses `P0/P1/P2` instead of `High/Medium/Low` — an inconsistency, not an intentional variant. `High/Medium/Low` was chosen as the standard because it matches both #9 and #11, and also matches the Priority field already used on the Ideas board itself, so the vocabulary is consistent from WAG stage through delivery.

**How to apply:** New delivery boards should be created with this layout from the start. #8 should be reconciled to `High/Medium/Low` when next touched (not urgent enough alone to warrant a one-off migration pass). Milestones on these boards are named per [[feedback_milestone_naming_convention]].

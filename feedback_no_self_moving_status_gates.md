---
name: feedback_no_self_moving_status_gates
description: "An AI must not move a project/issue Status field past a human-verification gate (e.g. into 'In QA', 'Done') on its own — draft the verification artifact and ask the human to move it"
metadata: 
  node_type: memory
  type: feedback
  modified: 2026-08-05T11:08:34.964Z
  originSessionId: 37ed054a-fbd2-48ae-b6fa-8935b7b9001a
---

When implementing a story/ticket, don't move its project board `Status` field (or any equivalent field) past whatever value represents human verification — e.g. into `In QA` or `Done` on a delivery board (see [[methodology_traditional_project_board_layout]]). Draft or attach the verification artifact instead (a test table, a checklist, a spec-conformance summary) and let the human move the card.

**Why:** Surfaced on YnabSharp PR#117 (2026-07-31) — after running a DTO-vs-spec check and judging it a pass, I moved the linked issue's `Status` field to `In QA` myself, with no human in the loop. The user objected directly ("I don't like that you marked your own homework"). This is the same failure as an AI approving its own PR, just via a board field instead of an approve button — it doesn't read like a sign-off, but it asserts the same thing.

This was originally filed as [SoloCAIRN#18](https://github.com/joshuaedwardcrowe/SoloCAIRN/issues/18) and nearly fixed there (PR#22, closed unmerged 2026-08-05) — wrong home. SoloCAIRN's own scope doc (`docs/10-what-cairn-does-not-solve.md`) excludes "conventions and standards" (§1) and "AI tool selection and governance" (§8); *which tool, which field, which board* represents a verification gate is exactly that kind of concrete tooling detail. The general principle (AI shouldn't self-verify) is genuinely SoloCAIRN's lane and is already stated there, correctly, in the abstract ("Letting AI sign off. A test pass from AI is input to your decision, not the decision."). The *concrete* rule — don't touch the Status field yourself — is Joshua's own board-tooling convention, same shape as [[methodology_idea_board_layout]] and [[methodology_traditional_project_board_layout]]. This was also a repeat of an already-documented mistake: see [[methodology_four_homes_framework]]'s "third occurrence" entry, which flagged this exact incident's routing as wrong on the day it happened — the fix wasn't actually applied until 2026-08-05, several days and one drafted-then-closed PR later, because the tripwire existed but wasn't checked before acting.

**How to apply:** Whenever a Status/pipeline field exists on a project board and one of its values represents completed human verification, treat that value as off-limits for self-assignment — regardless of which repo, which board, or what the gate is called (`In QA`, `Done`, `SWAG'd / Prioritized` alongside its own [[methodology_engineering_estimation_pipeline]] gate, etc.). Attach the evidence, ask the human to move it.

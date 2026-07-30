---
name: feedback_idea_routing
description: "Future feature/idea mentions belong on the GitHub Ideas project board as an issue, not saved into JoshuaBrain memory"
metadata: 
  node_type: memory
  type: feedback
  originSessionId: f401e5ac-4951-45c1-93a4-68d32a637226
  modified: 2026-07-30T00:42:51.498Z
---

When the user floats a future feature idea in conversation (not yet a task, not yet a WAG), create it as a GitHub issue and add it to the relevant Ideas project board — do not just write it into memory as a project-context note.

**Why:** Memory is for context that helps future conversations, not a substitute for the actual backlog tracking system. Ideas live in GitHub Projects so they're visible, prioritized, and flow into the [[methodology_engineering_estimation_pipeline]] (WAG → SWAG → spike → estimates). Corrected 2026-07-30 after saving a SpendfulnessCli command idea straight to memory instead of the board.

**How to apply:** There are two Ideas boards — GitHub Project #10 "Ideas" (owner: joshuaedwardcrowe) for personal-account repos (SpendfulnessCli, YnabSharp, SoloCAIRN, JoshuaBrain), and org-owned repos (KitCli, Diagnosea) get their own separate Ideas board — check the repo's org before routing. Match existing item conventions on the board: plain-language pre-WAG issue title (see [[methodology_issue_title_convention]]), "User Value" label (plus a type label like "New Command" if applicable), and a body noting it's "not shaped yet... needs a WAG before anything else" plus any known blocking dependency. Only fall back to a memory note if there's no repo/board to attach the idea to.

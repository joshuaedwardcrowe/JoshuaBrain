---
name: feedback_idea_routing
description: "Future feature/idea mentions belong on a GitHub Ideas project board as an issue, not saved into JoshuaBrain memory"
metadata: 
  node_type: memory
  type: feedback
  modified: 2026-08-05T10:59:03.055Z
  originSessionId: 37ed054a-fbd2-48ae-b6fa-8935b7b9001a
---

When the user floats a future feature idea in conversation (not yet a task, not yet a WAG), create it as a GitHub issue and add it to the relevant Ideas project board — do not just write it into memory as a project-context note.

**Why:** Memory is for context that helps future conversations, not a substitute for the actual backlog tracking system. Ideas live in GitHub Projects so they're visible, prioritized, and flow into the [[methodology_engineering_estimation_pipeline]] (WAG → SWAG → spike → estimates).

**How to apply:** Every repo has its own Ideas board by default (see [[methodology_idea_board_layout]] for the full list and layout) — route the issue there first. Only use the shared personal-account board (`https://github.com/users/joshuaedwardcrowe/projects/10`) when the idea genuinely doesn't pertain to one specific repo. SoloCAIRN has no Ideas board at all — its idea-stage issues get worked through directly, not staged through WAG/SWAG. Match existing item conventions on whichever board it lands on: plain-language pre-WAG issue title (see [[methodology_issue_title_convention]]) and a body noting it's "not shaped yet... needs a WAG before anything else" plus any known blocking dependency, with labels matching the source repo's own taxonomy (not a forced universal label — see [[methodology_idea_board_layout]]). Only fall back to a memory note if there's no repo/board to attach the idea to at all.

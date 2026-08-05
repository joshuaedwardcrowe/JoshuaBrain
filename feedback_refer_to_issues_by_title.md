---
name: feedback_refer_to_issues_by_title
description: "When discussing a GitHub issue with the user, lead with its title, not the bare issue number"
metadata: 
  node_type: memory
  type: feedback
  modified: 2026-08-05T10:14:35.884Z
  originSessionId: 37ed054a-fbd2-48ae-b6fa-8935b7b9001a
---

When referring to a GitHub issue in conversation, use its title (optionally with the number alongside, e.g. "No way for Claude to connect to a YNAB budget" (#151)) — never the bare number alone.

**Why:** The user made this point twice in one conversation (2026-08-05, YnabSharp#151): first arguing that a future "what's the priority on #25893829?" is meaningless without a legible title — which is the whole reason [[methodology_issue_title_convention]]'s idea-stage titles must be plain-language problem statements, not solution names. Then, immediately after getting the issue retitled for exactly that reason, caught me still calling it "#151" in the next message — the same failure the retitle was meant to fix, recurring immediately after the point was made.

**How to apply:** Once an issue has a legible title, use it (or title + number) in every reference from then on, including in the same turn a retitle happens. Bare numbers are only acceptable in raw command arguments (`gh issue edit 151 ...`), never in text addressed to the user.

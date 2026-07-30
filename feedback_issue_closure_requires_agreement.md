---
name: feedback-issue-closure-requires-agreement
description: "Never word a PR/summary as 'closing' an issue, and never use GitHub auto-close keywords, until the user has agreed the PR actually resolves it"
metadata: 
  node_type: memory
  type: feedback
  originSessionId: 8ca57252-6b27-4f26-9743-8937583c0505
  modified: 2026-07-30T20:06:25.785Z
---

Don't use GitHub closing keywords (`closes #N`, `fixes #N`, `resolves #N`) in a PR body, and don't describe a PR as "closing" an issue in a summary to the user — even if merge is still pending and even if the wording is technically just loose phrasing rather than a real auto-close trigger.

**Why:** Caught 2026-07-30 on [[project_spendfulnesscli_issue_tracking]]-adjacent work (YnabSharp#79/PR#109) — I summarized a just-opened PR as "closing #79" despite not having merged yet, let alone had the user review it. The user compared this to Jira: a ticket doesn't move to Done at PR-open, or even at merge — it moves to Done when the reporter/reviewer agrees the delivered work actually satisfies it. Issue closure is a distinct acceptance step, not a side effect of code being merged.

**How to apply:** In PR bodies, reference issues neutrally ("Linked issue: #N", "Relates to #N") rather than with auto-close keywords. In summaries to the user, say a PR "addresses" or "targets" an issue, never that it "closes" or "resolves" one, until the user has explicitly signed off post-review that the issue is done. Closing the issue itself is then a separate, explicit action — don't do it automatically alongside a merge.

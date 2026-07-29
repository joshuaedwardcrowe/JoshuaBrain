---
name: feedback-spike-outcome-rule
description: "A spike resolves to one of two outcomes — new complexity found, or no new complexity — and \"no new complexity\" means close the spike and open a fresh ticket for backlog refinement"
metadata: 
  node_type: memory
  type: feedback
  originSessionId: 681f9a31-eb28-4ccf-8913-2eb0f7bd2929
  modified: 2026-07-29T23:29:51.102Z
---

A spike (investigation) concludes with a binary outcome:

- **No new complexity** — the investigation confirms the work is as scoped/simple as expected. Close the spike issue and open a fresh, cleanly-titled delivery-stage ticket (per [[methodology_issue_title_convention]] — `type(scope): description`) for the actual build. That new ticket gets sized in a backlog refinement session, not the spike itself.
- **New complexity** — not yet specified by the user as of 2026-07-29; don't assume a procedure for this branch, ask when it comes up.

**Why:** Stated directly by the user (2026-07-29) as a general rule, in the context of resolving issue #59 (YnabSharp's Money Movements investigation) — the investigation found the work was genuinely scoped and buildable with no hidden wrinkles, so per this rule it should close and hand off to a new ticket rather than being retitled/reused in place.

**How to apply:** When a spike/investigation-type issue concludes, don't retitle or repurpose it in place. Ask (or determine from the findings) whether the outcome is "new complexity" or "no new complexity" — on the latter, close the spike with a link to a freshly-created, properly-titled ticket, and leave that ticket unestimated until an actual backlog refinement session sizes it. This is a general process rule (across repos), not specific to YnabSharp or this one investigation.

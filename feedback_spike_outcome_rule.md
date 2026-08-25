---
name: feedback-spike-outcome-rule
description: "A spike resolves to new complexity or no new complexity; the verdict asks whether the work is as small as the issue assumed, and each branch has its own procedure"
metadata: 
  node_type: memory
  type: feedback
  originSessionId: 681f9a31-eb28-4ccf-8913-2eb0f7bd2929
  modified: 2026-08-25T19:55:00.000Z
---

A spike (investigation) concludes with a binary outcome:

- **No new complexity** — the investigation confirms the work is as scoped/simple as expected. Close the spike issue and open a fresh, cleanly-titled delivery-stage ticket (per [[methodology_issue_title_convention]] — `type(scope): description`) for the actual build. That new ticket gets sized in a backlog refinement session, not the spike itself.
- **New complexity** — the issue that prompted the spike stays open as the parent, and the build hangs off it as sub-issues in delivery order. The spike issue still closes; it answered its question, and per the rule above is never reused in place.

**The verdict asks whether the work is as small as the issue assumed** — not whether the spike's design questions got answered. A spike that answers every open question and still uncovers four tickets, an ADR, a prerequisite and a blocker found new complexity. Judging by "nothing is unresolved" instead of "nothing grew" produces the wrong verdict (KitCli#148, 2026-08-25).

Precedent for the breakdown shape: KitCli#136 (investigation 0002) stayed open on the Ideas board with nine sub-issues carrying the work.

**Why:** Stated directly by the user (2026-07-29) as a general rule, in the context of resolving issue #59 (YnabSharp's Money Movements investigation) — the investigation found the work was genuinely scoped and buildable with no hidden wrinkles, so per this rule it should close and hand off to a new ticket rather than being retitled/reused in place.

**How to apply:** When a spike/investigation-type issue concludes, don't retitle or repurpose it in place. Ask (or determine from the findings) whether the outcome is "new complexity" or "no new complexity" — on the latter, close the spike with a link to a freshly-created, properly-titled ticket, and leave that ticket unestimated until an actual backlog refinement session sizes it. This is a general process rule (across repos), not specific to YnabSharp or this one investigation.

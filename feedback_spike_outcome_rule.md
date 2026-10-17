---
name: feedback-spike-outcome-rule
description: "A spike resolves to new complexity (new code must be written to achieve it) or no new complexity (what exists already does it); each branch has its own procedure"
metadata: 
  node_type: memory
  type: feedback
  originSessionId: 681f9a31-eb28-4ccf-8913-2eb0f7bd2929
  modified: 2026-10-17T00:00:00.000Z
---

A spike (investigation) concludes with a binary outcome:

- **No new complexity** — what already exists achieves it; the work is using it, documenting it or configuring it. Close the spike issue and open a fresh, cleanly-titled delivery-stage ticket (per [[methodology_issue_title_convention]] — `type(scope): description`) for that work. That new ticket gets sized in a backlog refinement session, not the spike itself.
- **New complexity** — new code must be written to achieve it. The issue that prompted the spike stays open as the parent, and the build hangs off it as sub-issues in delivery order. The spike issue still closes; it answered its question, and is never reused in place.

**The verdict asks whether new code is needed** — not whether the spike's design questions got answered, and not whether an issue guessed the size. A spike that answers every open question and still needs new types, a new interface method and an ADR found new complexity (KitCli#148).

**A spike that finds both splits in two.** When part of the goal works with what exists and part needs new code, write two investigations, one verdict each, rather than one doc whose verdict flips on which part the reader cares about (KitCli return-to investigation, 2026-10-17).

Precedent for the breakdown shape: KitCli#136 (investigation 0002) stayed open on the Ideas board with nine sub-issues carrying the work.

**Why:** The two-outcome rule was stated by the user (2026-07-29) resolving YnabSharp #59. The definition was stated by the user on 2026-10-17: "New complexity is when new code needs to be written to achieve something."

**How to apply:** When a spike/investigation-type issue concludes, don't retitle or repurpose it in place. Decide the verdict by asking "does this need code that doesn't exist yet?" On no new complexity, close the spike with a link to a freshly-created, properly-titled ticket, and leave that ticket unestimated until an actual backlog refinement session sizes it. This is a general process rule across repos.

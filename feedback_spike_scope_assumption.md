---
name: feedback_spike_scope_assumption
description: "A technical spike isn't done at a verdict — its written finding must reach the same implementation-level resolution the throwaway code did. Canonical text lives in SoloCAIRN, not here."
metadata: 
  node_type: memory
  type: feedback
  originSessionId: 9c6b45a7-a253-4f6b-a0fa-ac50bd7f8c3d
  modified: 2026-08-05T11:55:52.355Z
---

A technical spike's write-up must carry implementation-level resolution — the actual interface, constraint, or thing that did or didn't work — not a verdict one level up from it ("MCP supports confirmation" vs. "the C# SDK exposes `server.ElicitAsync(...)` for exactly this"). A finding that stops at the verdict looks broad or narrow arbitrarily, because the specificity that would show its real reach never got written down. Reaching implementation-level detail is what makes a finding's downstream impact visible — breadth isn't something to assume upfront, it falls out once the resolution is actually concrete.

**Canonical location:** [SoloCAIRN PR#21](https://github.com/joshuaedwardcrowe/SoloCAIRN/pull/21) (`docs/03-lifecycle.md`, the "Spikes: write the finding down" section) — this passed the four-homes test as genuinely solo-maintainer-general, not JoshuaBrain-personal, so the durable text lives there once merged, not duplicated here. This entry exists only to record that the rule was first (mis)formulated as "assume broad scope by default" in this repo before the sharper framing replaced it — see [[methodology_four_homes_framework]]'s fourth recurrence for how that placement mistake happened, and [[feedback_spike_outcome_rule]] for the related rule on how a spike concludes.

**How to apply:** Don't restate this rule's content from memory — read SoloCAIRN's current `docs/03-lifecycle.md` for the live text, since it may be edited there independent of this file.

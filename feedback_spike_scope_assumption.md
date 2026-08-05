---
name: feedback_spike_scope_assumption
description: "Default assumption when scoping what a spike's findings affect: assume the whole build/plan, not just the one ticket that seemed to be waiting on the answer"
metadata: 
  node_type: memory
  type: feedback
  originSessionId: 9c6b45a7-a253-4f6b-a0fa-ac50bd7f8c3d
  modified: 2026-08-05T11:45:10.643Z
---

When a spike investigation produces a finding, don't scope its impact to the single ticket that appeared to be blocked on it. Default to assuming a spike's findings ripple across the whole plan — architecture, other tickets, scope itself — until a finding is demonstrably narrow. Narrow-by-default is backwards: the reason something is *in* a spike rather than already a scoped ticket is precisely that its blast radius is unknown going in.

**Why:** Corrected 2026-08-05 during the YnabSharp#151 Claude↔YNAB MCP spike. I framed "does MCP have a built-in tool-call approval mechanism" as feeding only the write-access ADR. It actually reshaped the ADR's answer, the MCP scaffold ticket's technical shape (write tools need `ElicitAsync` wired in, not just a policy statement), and the annotation requirements on every tool including the read-only ones. The user called this out directly: assume a spike's findings touch the whole build, don't narrow prematurely.

**How to apply:** When reporting spike findings mid-investigation, describe which parts of the *whole plan* a finding touches, not just the ticket that prompted the question. Re-check every ticket already sketched in the spike's sequence against a new finding before declaring the finding's scope closed. See [[feedback_spike_outcome_rule]] for the related rule on how a spike concludes.

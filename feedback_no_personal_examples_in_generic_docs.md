---
name: feedback-no-personal-examples-in-generic-docs
description: "Keep real personal examples out of generic/methodology docs (like SPENDFULNESS.md) — abstract them, even if mundane"
metadata: 
  node_type: memory
  type: feedback
  originSessionId: 85b9838c-1121-4dca-bcfd-35622148bc62
  modified: 2026-08-05T15:16:40.025Z
---

Generic/methodology docs meant to teach a reusable approach (e.g. SpendfulnessCli's SPENDFULNESS.md) should use abstract illustrative examples, not the user's real personal details lifted verbatim from conversation — even mundane-seeming ones (a specific daily snack habit, in this case).

**Why:** Caught mid-edit — a real personal reasoning example ("I buy a daily chocolate bar") got written directly into SPENDFULNESS.md, a public repo doc meant to generalize a naming methodology, not narrate the author's private habits. The distinction isn't "public repo" vs. "private repo" — it's generic/methodology doc vs. personal-instance doc. Personal-instance docs (e.g. my-financial-map's own README, which *is* one person's real budget map) are the correct place for real specifics; SPENDFULNESS.md already uses abstract examples elsewhere ("a coffee, a haircut") and new additions should match that. Related: [[methodology_four_homes_framework]] draws a similar line between doc types by scope.

**How to apply:** Before writing user-supplied reasoning or examples into a generic/methodology doc, check whether the doc teaches a reusable approach or documents one person's actual situation. If it's the reusable kind, abstract any real personal detail into a generic placeholder before it goes in — don't wait to be asked.

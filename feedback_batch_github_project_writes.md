---
name: feedback_batch_github_project_writes
description: "Batch GitHub Project board writes into one aliased GraphQL request; looping `gh project item-add`/`item-edit` per issue exhausts the 5,000/hr rate limit"
metadata: 
  node_type: memory
  type: feedback
  originSessionId: a94b8a33-12ae-450e-8ceb-ea3d391fa209
  modified: 2026-08-23T22:35:00.000Z
---

Never loop `gh project item-add` / `gh project item-edit` once per issue when populating or re-cutting a board. Build one GraphQL request with aliased mutations and send it in a single call.

```graphql
mutation {
  a1: addProjectV2ItemById(input: {projectId: "PVT_…", contentId: "I_…"}) { item { id } }
  a2: addProjectV2ItemById(input: {projectId: "PVT_…", contentId: "I_…"}) { item { id } }
}
```

Then a second batched mutation of `updateProjectV2ItemFieldValue` aliases to set every Estimate and Priority at once. Two requests instead of three per issue.

**Why:** 2026-08-23, KitCli backlog calibration. Populating ~50 issues across seven boards took three CLI invocations each — add, set estimate, set priority — and each `gh project` call spends **both** a core and a GraphQL unit. Combined with verification listings after every stage, and with the whole population run **twice** (once grouped by decision-theme, then re-cut by domain after the grouping changed), this burned the entire 5,000/hr core allowance twice in one session, stalling the work ~15 minutes each time. `gh api rate_limit --jq '.resources'` shows core and graphql separately and is itself free to call.

**How to apply:** For anything touching more than ~5 board items, write the batched GraphQL rather than a shell loop. Query `gh api rate_limit` before starting a bulk operation and estimate the cost against what's left. And note the non-technical half: the second run existed only because the first one populated boards before the structure was agreed — see [[feedback_no_process_without_a_consumer]] for the adjacent habit of building before the shape is settled.

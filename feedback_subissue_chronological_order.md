---
name: feedback-subissue-chronological-order
description: Sub-issue breakdowns must represent provable chronological delivery order; new projects start with a planning spike
metadata: 
  node_type: memory
  type: feedback
  originSessionId: 681f9a31-eb28-4ccf-8913-2eb0f7bd2929
  modified: 2026-07-29T23:30:03.665Z
---

When breaking a `User Value` issue into sub-issues (across any repo, not just SpendfulnessCli), the sub-issues must represent a chronological delivery order — the order they'd actually need to be built in, not just a logical decomposition of the feature.

**Why:** The user stated this as a hard rule (2026-07-28): decomposing an issue into sub-issues without first jointly planning the work risks an ordering that can't be proven correct — e.g. proposing a report command before the data-parsing piece it depends on. This came up when I asked whether to decompose issue #191 (SpendfulnessCli) into sub-issues immediately; the user pushed back because we hadn't planned the delivery order together yet.

**How to apply:** Do not propose or create a sub-issue breakdown solo. Before decomposing any `User Value`/story-shaped issue into sub-issues, do the planning collaboratively with the user first — e.g. via a dedicated planning-spike issue/session — and only create sub-issues once delivery order is agreed. As a related convention: **each new GitHub project should start with a planning spike** (a `Spike`-labeled issue) — create and add the spike to the project *before* populating it with other issues, not after. (I got this sequencing backwards once already — 2026-07-28, creating project #9 and adding 10 issues before creating the spike — caught by the user afterward.)

Per [[methodology_engineering_estimation_pipeline]] (revised 2026-07-29 to be genuinely Agile): don't plan a whole milestone's full ticket order in one big upfront spike — only the next handful of tickets need full ordering/estimates at a time, refined incrementally as work proceeds (just-in-time backlog refinement). The joint-planning rule above still applies to whatever's being ordered at that moment; it just no longer means "produce the entire milestone's order in one sitting."

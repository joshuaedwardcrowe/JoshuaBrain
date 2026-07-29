---
name: project-spendfulnesscli-mission
description: "SpendfulnessCli's guiding mission is to help users be \"spendful\" per the framework in SPENDFULNESS.md"
metadata: 
  node_type: memory
  type: project
  originSessionId: 681f9a31-eb28-4ccf-8913-2eb0f7bd2929
  modified: 2026-07-28T18:01:21.309Z
---

SpendfulnessCli (~/Documents/GitHub/SpendfulnessCli) is built around a mission, not just bookkeeping: helping people be "spendful" — aligning spending with personal values rather than guilt-based tracking. The framework is documented in `SPENDFULNESS.md` (added 2026-07-28) and analyzes transactions across four axes: Target (what), Behaviour (how/routine vs one-off), Situation (context), and Motivation (why). It maps onto YNAB's structure (Category Group/Category/Memo/Memo tags like `#aligned`/`#misaligned`).

**Why:** The user stated explicitly this is "the mission behind the CLI," not just an ad-hoc doc — it should shape feature priorities and framing, not just be treated as one file among many.

**How to apply:** When suggesting features, CSV/export formats, or analysis tooling for this CLI, favor ones that support surfacing alignment/misalignment (e.g. `#aligned`/`#misaligned` tag filtering) and the four-axis taxonomy over generic budgeting features. Treat "spendful" framing as a first-class concept when naming things or writing docs in this repo.

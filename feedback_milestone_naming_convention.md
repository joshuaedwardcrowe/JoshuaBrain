---
name: feedback-milestone-naming-convention
description: "Milestones tied to an external spec/version should be named after that version, not a goal description"
metadata: 
  node_type: memory
  type: feedback
  originSessionId: 681f9a31-eb28-4ccf-8913-2eb0f7bd2929
  modified: 2026-07-29T18:01:00.099Z
---

When a milestone's scope is defined by catching up to (or tracking) an external spec/API version, name the milestone after that version (e.g. `YNAB API v1.86.0`), not a goal-style description (e.g. `Full YNAB API Coverage`).

**Why:** The user corrected this directly (2026-07-29) when I named a YnabSharp milestone "Full YNAB API Coverage." A version-anchored name pins the milestone to a concrete, checkable target and naturally supports a version history over time (e.g. a future `YNAB API v1.87.0` milestone when the spec moves again), where a goal-style name reads as open-ended and doesn't communicate which spec snapshot it's actually targeting.

**How to apply:** For YnabSharp (or any repo tracking an external API/spec), name milestones after the spec version being targeted. This likely generalizes to other external-dependency-driven milestones too — prefer the concrete version/target name over a descriptive goal name when one is available.

---
name: feedback-issue-title-convention
description: "Two-stage issue title convention — plain-language problem statements pre-WAG, Conventional Commits style once a spike carves out delivery sub-issues"
metadata: 
  node_type: memory
  type: feedback
  originSessionId: 681f9a31-eb28-4ccf-8913-2eb0f7bd2929
  modified: 2026-07-28T20:20:23.012Z
---

Issue titles across KitCli, YnabSharp, and SpendfulnessCli follow a two-stage convention (documented in each repo's `CONTRIBUTING.md`, 2026-07-28):

- **Idea-stage** (unvalidated, pre-WAG — see [[feedback_engineering_estimation_pipeline]]) — plain-language problem statements, e.g. "No way to X" / "Y doesn't handle Z". This is deliberate: an idea is a pitch for an unmet need, not yet a scoped unit of work.
- **Delivery-stage sub-issues** (carved out by a planning spike once an idea is greenlit — see [[feedback_subissue_chronological_order]]) — Conventional Commits style, matching PR titles: `type(scope): description`, e.g. `feat(reporting): add loan-to-value command`.

SpendfulnessCli didn't have a `scope` taxonomy before this (unlike KitCli's abstractions/instructions/commands/workflow/host/tooling or YnabSharp's client/domain/seeder/tooling) — it now uses its `Commands.*` project folders as scopes: `chat`, `export`, `organisation`, `personalisation`, `reporting`, `reusable`. SpendfulnessCli's PR titles were also brought in line with Conventional Commits as part of this (previously undocumented there, unlike KitCli/YnabSharp).

**Why:** The user noticed the "No Way to X" pattern across many existing SpendfulnessCli issue titles and wanted a deliberate, documented practice rather than an accidental one — landed on GitHub's own "issue" framing (a problem) for the pitch stage, and their own Jira-ticket familiarity (Conventional Commits, which they already liked for commit/PR titles) for the delivery stage.

**How to apply:** Don't rename existing idea-stage issue titles to match this retroactively — the convention governs new titles and new delivery-stage sub-issues, not a backfill of old ones. When a planning spike concludes and carves out real sub-issues, title them `type(scope): description`, not as another "No way to X" restatement.

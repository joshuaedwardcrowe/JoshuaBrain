---
name: project-spendfulnesscli-kitcli-split-history
description: "SpendfulnessCli predates KitCli — it was split out, so old SpendfulnessCli issues can actually be framework-level concerns misfiled in the wrong repo"
metadata: 
  node_type: memory
  type: project
  originSessionId: 681f9a31-eb28-4ccf-8913-2eb0f7bd2929
  modified: 2026-07-28T20:02:14.942Z
---

SpendfulnessCli is the original repository; KitCli was later extracted out of it as its own separate framework/org (github.com/KitCli/KitCli). See [[project_kitcli_vision]] for what KitCli is meant to be.

**Why this matters:** Older open issues in SpendfulnessCli (filed before the split) can describe problems that are actually about the CLI framework itself — command dispatch, workflow/side-effects, argument parsing, artefact/outcome plumbing — not about YNAB/spendfulness domain logic. These are migration residue: filed in the only repo that existed at the time, now homeless in the wrong place post-split. First concrete instance found (2026-07-28): issue #170 "Paginated List Commands" turned out to be fully implemented in KitCli's `Artefacts/Page/` with no concept doc — filed a fresh `docs` issue in KitCli (KitCli#62) and closed #170 in SpendfulnessCli once linked.

**How to apply:** When triaging open SpendfulnessCli issues (see [[project_spendfulnesscli_issue_tracking]]), watch for titles describing generic command/workflow/infrastructure behavior rather than YNAB-specific domain behavior — these are candidates to migrate (file fresh in KitCli using its type/area/severity label scheme, then close the SpendfulnessCli original with a link), not to triage into a SpendfulnessCli-scoped project. Likely candidates flagged during the open-issue audit: #159/#160 ("Workflow: Side Effects" / its spike — squarely `area:workflow`), #38 ("No Basic Sort Column / Order for all Commands" — cross-cutting command behavior), #29 ("Command Infrastructure Does Not Handle If Invalid Argument Passed"), #135 ("Use UserSecrets to Automatically Ingest Config Values" — generic config/DI, not YNAB-specific).

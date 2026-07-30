---
name: methodology_docs_folder_layout
description: "Standard docs/ folder structure (adr/, concepts/, reviews/ with 0000-template.md seeds) used by YnabSharp and KitCli; SpendfulnessCli intentionally stays on an older flat layout"
metadata:
  node_type: memory
  type: feedback
  subtype: methodology
  originSessionId: f401e5ac-4951-45c1-93a4-68d32a637226
  modified: 2026-07-30T06:37:12.652Z
---

Confirmed directly against the repos (2026-07-30) rather than assumed — two distinct layouts exist, not one universal convention:

**Current standard — YnabSharp, KitCli:** a `docs/` folder containing three subfolders:
- `docs/adr/` — sequentially numbered ADRs (`0001-title.md`), seeded with a `0000-template.md`
- `docs/concepts/` — one file per concept, topic-named (not numbered), also seeded with a `0000-template.md`
- `docs/reviews/` — dated architectural reviews (`YYYY-MM-DD-architectural-review.md`)

Repos add their own extra reference material directly under `docs/` alongside these three (YnabSharp: `ynab-api-coverage.md`, `ynab-openapi-spec.yaml`; KitCli: `dependency-graph.drawio`/`.png`, `operating-model-rollout-status.md`).

**Older layout — SpendfulnessCli:** no `docs/` folder. Top-level `ADR/` (files `ADRxx-Title.md`, no template seed) + top-level `CONCEPTS.md` (a single file, not a folder) + `FUTURE-ADR.md`. No `reviews/` equivalent.

**Why:** SpendfulnessCli predates KitCli (see [[project_spendfulnesscli_kitcli_split_history]]) and its own CONTRIBUTING.md states the process is "deliberately lighter than KitCli's or YnabSharp's" — this is a stated intentional choice, not an unmigrated gap. The `docs/{adr,concepts,reviews}` + template-seed pattern is Joshua's personal preference for how newer/heavier repos organize documentation — it's a [[methodology_four_homes_framework|JoshuaBrain-level]] working style, not something SoloCAIRN should prescribe (SoloCAIRN cares about the Build-stage lifecycle, not specific folder names).

**How to apply:** When bootstrapping docs for a new or under-documented repo (e.g. the Diagnosea repos in [[project_diagnosea_contributing_bootstrap]]), default to the YnabSharp/KitCli `docs/{adr,concepts,reviews}` structure with `0000-template.md` seeds — that's the current standard, not SpendfulnessCli's flat layout. Don't treat SpendfulnessCli's layout as something to migrate to the new structure either, unless Joshua says so — its own docs explicitly justify staying lighter.

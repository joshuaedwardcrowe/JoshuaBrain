---
name: methodology_docs_folder_layout
description: "Standard docs/ folder structure (adr/, concepts/, reviews/ with 0000-template.md seeds) used by YnabSharp and KitCli; SpendfulnessCli intentionally stays on an older flat layout"
metadata:
  node_type: memory
  type: feedback
  subtype: methodology
  originSessionId: f401e5ac-4951-45c1-93a4-68d32a637226
  modified: 2026-08-05T15:10:44.615Z
---

Confirmed directly against the repos (2026-07-30) rather than assumed — two distinct layouts exist, not one universal convention:

**Current standard — YnabSharp, KitCli, SpendfulnessCli:** a `docs/` folder containing four subfolders:
- `docs/adr/` — sequentially numbered ADRs (`0001-title.md`), seeded with a `0000-template.md`
- `docs/concepts/` — one file per concept, topic-named (not numbered), also seeded with a `0000-template.md`
- `docs/reviews/` — dated, multi-finding architectural reviews (`YYYY-MM-DD-architectural-review.md`), not single-topic write-ups
- `docs/investigations/` — sequentially numbered (`0001-question.md`), seeded with a `0000-template.md`; what a technical spike produces, ships via PR with a Status. Added to SpendfulnessCli 2026-08-02 (#199) but not propagated to YnabSharp/KitCli until 2026-08-05 — a real cross-repo-propagation miss, not an intentional gap. See [[methodology_cross_repo_propagation]].

Repos add their own extra reference material directly under `docs/` alongside these three (YnabSharp: `ynab-api-coverage.md`, `ynab-openapi-spec.yaml`; KitCli: `dependency-graph.drawio`/`.png`, `operating-model-rollout-status.md`).

**Older layout — SpendfulnessCli (a gap, not an intentional exception):** no `docs/` folder. Top-level `ADR/` (files `ADRxx-Title.md`, no template seed) + top-level `CONCEPTS.md` (a single file, not a folder) + `FUTURE-ADR.md`. No `reviews/` equivalent. Corrected 2026-07-30: this was initially assumed to be an intentional choice because SpendfulnessCli's CONTRIBUTING.md says its process is "deliberately lighter than KitCli's or YnabSharp's" — but that line is about *process* (no CI, no required review, docs-only changes go straight to `main`), not about folder layout. Nothing justifies the flat layout specifically; it's unmigrated legacy from before the `docs/{adr,concepts,reviews}` pattern existed (see [[project_spendfulnesscli_kitcli_split_history]]).

**Why:** The `docs/{adr,concepts,reviews}` + template-seed pattern is Joshua's personal preference for how repos organize documentation — a [[methodology_four_homes_framework|JoshuaBrain-level]] working style, not something SoloCAIRN should prescribe (SoloCAIRN cares about the Build-stage lifecycle, not specific folder names). It applies to every repo, including SpendfulnessCli.

**How to apply:** When bootstrapping docs for a new or under-documented repo (e.g. the Diagnosea repos in [[project_diagnosea_contributing_bootstrap]]), default to the YnabSharp/KitCli `docs/{adr,concepts,reviews}` structure with `0000-template.md` seeds. SpendfulnessCli migrating its `ADR/`+`CONCEPTS.md` into that structure is tracked as an idea on the [Ideas board](https://github.com/users/joshuaedwardcrowe/projects/10), not left unresolved in this memory.

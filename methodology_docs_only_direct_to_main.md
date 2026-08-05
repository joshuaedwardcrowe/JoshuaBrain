---
name: methodology_docs_only_direct_to_main
description: "Docs-only changes (README, CONTRIBUTING.md, ADRs, concept docs) can be committed straight to main, skipping the PR — across every repo"
metadata: 
  node_type: memory
  type: feedback
  subtype: methodology
  modified: 2026-08-05T10:21:39.398Z
  originSessionId: 37ed054a-fbd2-48ae-b6fa-8935b7b9001a
---

Docs-only changes can be committed straight to `main`, bypassing the branch + PR flow that every other change goes through.

**Why:** SpendfulnessCli's `CONTRIBUTING.md` already carried this exception. Extended to YnabSharp and KitCli on 2026-08-05 (prompted by a `CONTRIBUTING.md` update for [[methodology_engineering_estimation_pipeline]]'s new Priority gate) after the user pointed out that requiring a PR for pure documentation is PR inflation — PRs should be reserved for code changes that actually need review, not text that only needs to be correct. Confirmed this doesn't need per-repo judgment: KitCli's branch protection isn't actually configured to block it even though its docs claimed review was enforced, and YnabSharp's required-status-check branch protection didn't block a direct docs-only push either — so the exception is safe to state uniformly.

**How to apply:** When a change is *only* to documentation (CONTRIBUTING.md, README, ADRs, concept docs, this kind of file) with no code/test/config touched, commit straight to `main` in any personal-account or KitCli-org repo rather than opening a PR. Mixed changes (code + docs together) still go through the normal PR flow — this exception is for docs-only commits specifically. See [[methodology_cross_repo_propagation]] — this was applied to all three repos carrying the estimation-pipeline doc in the same sitting it was decided, not just the one that triggered it.

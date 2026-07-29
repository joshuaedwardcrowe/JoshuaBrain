---
name: methodology-pr-size-limit
description: "PR size cap that applies across every repository, not just one project"
metadata: 
  node_type: memory
  type: feedback
  subtype: methodology
  originSessionId: 681f9a31-eb28-4ccf-8913-2eb0f7bd2929
  modified: 2026-07-29T23:28:19.483Z
---

Pull requests must stay small: **maximum 20 files changed, 10-15 files
preferred.** This applies across every repository worked on together,
not just one project — it's a general workflow rule, not a per-repo
convention. Large diffs are hard to review well no matter how "safe"
the content is.

**How to apply:**
- Before opening a PR, count files changed. If it's over ~15, look for
  a natural split (by layer/module, or stacked PRs) before defaulting
  to one big PR.
- For a refactor that's genuinely one atomic unit for the build to stay
  green (e.g. a cross-project rename with no back-compat shim, so every
  dependent project must be renamed in the same commit) — this is a
  real tension against the size cap. Don't silently pick a resolution
  (e.g. adding a temporary compatibility shim just to enable splitting,
  or accepting a red-CI window on an intermediate stacked PR) — surface
  the tradeoff and ask, since it affects git history/CI cleanliness in
  a way the user should decide, not just the file-count number.
- This is a hint to plan PR boundaries *before* starting a large piece
  of work, not just something to fix after the fact — for a big
  refactor, decide the split up front.

**Precedent:** on PR #68 (YnabSharp, 42 files — a whole-solution
mechanical `Budget`→`Plan` rename with a hard cross-project reference
and no back-compat shim), the user chose to keep it as one PR rather
than split via stacked/red-CI PRs or a throwaway shim. That's a
legitimate one-off exception where a clean split would require breaking
CI or writing throwaway code — it does not relax the cap for ordinary
work.

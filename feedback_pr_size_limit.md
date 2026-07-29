---
name: feedback-pr-size-limit
description: "PR size cap that applies across every repository, not just one project"
metadata: 
  node_type: memory
  type: feedback
  originSessionId: 8121d6e0-09a8-4ea6-827a-4c20a4a8d259
  modified: 2026-07-26T23:22:03.429Z
---

Pull requests must stay small: **maximum 20 files changed, 10-15 files
preferred.** This applies across every repository worked on together,
not just one project — it's a general workflow rule, not a per-repo
convention.

**Why:** the user rejected a 43-file PR (`YnabSharp` #68, a mechanical
`Budget`→`Plan` rename spanning the library, its Seeder, and docs) as
unacceptable regardless of how mechanical or low-risk the change was.
Large diffs are hard to review well no matter how "safe" the content.

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
- When asked, on PR #68 (YnabSharp, 42 files) the user chose to keep it
  as one PR rather than split via stacked/red-CI PRs or a throwaway
  shim — confirming that a whole-solution mechanical rename with a hard
  cross-project reference (CI builds the whole `.sln`, a dependent
  project directly references the renamed types, no back-compat shim in
  use) is a legitimate one-off exception to the cap. This does not
  relax the cap for ordinary work — still split by default whenever a
  clean split exists without breaking CI or requiring throwaway code.
- This is a hint to plan PR boundaries *before* starting a large piece
  of work, not just something to fix after the fact — for a big
  refactor, decide the split up front.

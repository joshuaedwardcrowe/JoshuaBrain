---
name: feedback-use-gh-stack-extension
description: "Stacked PRs use the gh stack extension, not hand-rolled base-branch chaining"
metadata: 
  node_type: memory
  type: feedback
  subtype: reactive
  originSessionId: 5be4966d-ae44-42f4-b84a-b40648b25c41
  modified: 2026-08-01T13:38:50.814Z
---

Stacked pull requests are a **first-class GitHub feature**, and the
`gh stack` extension (`github/gh-stack`) is **already installed**. Use it.
Do not hand-roll a stack by passing `--base <branch>` to `gh pr create`.

**Why:** base-chaining by hand produces the right topology but none of the
feature: no stack map in the merge box, no server-side cascading rebase, no
automatic re-targeting when a mid-stack PR merges, and nothing stopping a
dependent PR from being based on `main` by mistake. On 2026-08-01 (SpendfulnessCli
docs migration) I chained #197→#198→#199→#201 by hand but based #202 on `main`
even though it linked a file introduced by #201 — then wrote "merge this after
those" in the PR description instead of fixing the base. A note in a description
is not a constraint; a base branch is. GitHub's own docs:
<https://docs.github.com/en/pull-requests/get-started/about-stacked-prs>

**How to apply:**
- New work that needs splitting: `gh stack init b1 b2 b3` (bottom to top),
  then `gh stack submit`.
- Branches/PRs that already exist: `gh stack init` **adopts them
  automatically** — pass the existing branch names bottom-to-top, then
  `gh stack submit --auto`. It detects existing PRs, updates their bases,
  and links them without creating duplicates.
- `--auto` is required when not in an interactive terminal (the default
  opens a TUI editor needing Ctrl+S / Ctrl+B).
- Inspect with `gh stack view`; move around with `gh stack switch`.
- PRs must merge bottom-up; PRs above re-target automatically on merge.

Pairs with [[methodology_pr_size_limit]] — that rule says *when* to split
(over ~15 files, plan the split upfront); this one says *with what*.

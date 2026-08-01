---
name: feedback-check-pr-conventions-before-opening
description: "before opening a PR in any repo, check for a PR template and read a couple recent PR titles/bodies first — don't invent title/body format"
metadata: 
  node_type: memory
  type: feedback
  originSessionId: 8ca3fe47-e6cc-4b1e-9b8b-fb83a54a777d
  modified: 2026-08-01T08:02:48.215Z
---

Before running `gh pr create`, check for `.github/PULL_REQUEST_TEMPLATE.md`
and look at 2-3 recent merged PRs' titles and bodies (`gh pr view <n>
--json title,body`) in that repo. Use whatever structure they show —
don't default to an invented `## Summary` / `## Test plan` format.

**Why:** Opened YnabSharp PR #144 with a title missing the repo's
Conventional Commits prefix (see
[[feedback_commit_message_describes_change]]) *and* a made-up
`Summary/Test plan` body, when the repo actually has a strict
`.github/PULL_REQUEST_TEMPLATE.md` (`What/Why/Linked issue/How/Tested/
Kind of change`, title format enforced in an HTML comment at the top)
that recent PRs (#115, #117, #127) all follow closely. Both mistakes
were avoidable by reading the template and a couple of recent PRs
before creating the PR, not after the user flagged it.

**How to apply:** Applies across every repo, not just YnabSharp — same
spirit as [[methodology_pr_mirrors_issue_metadata]] (check per-repo
convention, don't assume). Do this check *before* the first
`gh pr create`, not as a fixup afterward.

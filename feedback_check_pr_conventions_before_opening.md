---
name: feedback-check-pr-conventions-before-opening
description: "Before opening a PR or filing/routing an issue, read that repo's template and CONTRIBUTING.md first — don't invent the format or the route"
metadata: 
  node_type: memory
  type: feedback
  originSessionId: 8ca3fe47-e6cc-4b1e-9b8b-fb83a54a777d
  modified: 2026-08-25T19:55:00.000Z
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

**The same rule governs filing and routing issues.** Read the repo's `CONTRIBUTING.md` and `.github/ISSUE_TEMPLATE/` before labelling an issue, putting it on a board, or deciding it needs a spike — not afterwards. On KitCli#147 (2026-08-25) this produced four mistakes at once: skipping the Ideas board and WAG that the Projects pipeline opens with, ignoring the feature request template's Problem/Proposed shape/Alternatives structure, putting an idea-stage plain-language title on a delivery board, and proposing a spike, which the pipeline places after greenlight. "Not sure that aligns with the CONTRIBUTING.md."

**How to apply:** Applies across every repo, not just YnabSharp — same
spirit as [[methodology_pr_mirrors_issue_metadata]] (check per-repo
convention, don't assume). Do this check *before* the first
`gh pr create`, not as a fixup afterward.

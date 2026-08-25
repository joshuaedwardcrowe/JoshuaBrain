---
name: feedback-pr-comment-audit
description: "A PR has two separate comment endpoints; query both, and always before merging, not only when asked to audit"
metadata: 
  node_type: memory
  type: feedback
  originSessionId: 8121d6e0-09a8-4ea6-827a-4c20a4a8d259
  modified: 2026-08-25T19:55:00.000Z
---

A GitHub pull request has **two independent comment endpoints**, and
checking only one misses real comments:

- `gh api repos/{owner}/{repo}/pulls/{pr}/comments` — inline review
  comments, anchored to a specific line/diff.
- `gh api repos/{owner}/{repo}/issues/{pr}/comments` — top-level PR
  conversation comments (a PR is an issue under the hood), not anchored
  to any line.

**Why:** on YnabSharp #68, three inline review comments got noticed,
replied to, and fixed — but a top-level comment ("What's the test
coverage of this PR?") sat unanswered because only the `pulls/.../comments`
endpoint was checked. The user had to point out the miss.

**Check both endpoints before merging, not only when asked to audit.** Merging is the moment the rule has to fire; framing it as an audit task means it fires only on request. On KitCli#149 (2026-08-25) CI went green and the merge followed immediately, with three inline review comments already sitting on the file — one of which invalidated a whole delivery ticket. "You did not look for them before blindly merging it."

**How to apply:** whenever auditing/replying to "all comments on a PR"
(this is what [[methodology_pr_size_limit]] and similar cross-repo rules
sit alongside), query both endpoints with `--paginate`, not just one.
Reply to inline comments via the pulls-comments `/replies` endpoint;
reply to top-level comments via a new `issues/{pr}/comments` POST. Both
get the same `🤖 **Claude:**` attribution prefix per repos that have
that convention (e.g. YnabSharp's CLAUDE.md).

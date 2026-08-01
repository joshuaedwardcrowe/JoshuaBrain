---
name: feedback-commit-message-describes-change
description: "Commit/PR titles must describe the actual change, not the process that produced it (e.g. \"address review\") — across every repo"
metadata: 
  node_type: memory
  type: feedback
  originSessionId: 641d09fd-5b56-4542-9ff6-f534d2afbc52
  modified: 2026-08-01T06:54:08.448Z
---

Commit and PR titles describe *what changed in the diff*, never the
process that produced it. "address review", "fix review comments",
"apply feedback" are all banned shapes — they tell a future reader
nothing without going and finding the review thread, and the whole
point of [[methodology_issue_title_convention]] / Conventional Commits
is that the title *is* the changelog line.

**Why:** Caught by the user on a real commit — `fix(tooling): address
review on spec schema resolver` — after a round of PR review fixes.
The same "don't reference the current task/fix" rule that applies to
code comments (explain the WHAT via the diff, not the WHY-this-exists
via a task reference) applies to commit messages too. The mistake was
mentally framing the commit as "the thing that resolves review
feedback" instead of describing the diff itself — easy to do right
after a batch of review-comment fixes, since the *reason* for the
commit is so present in context.

**How to apply:** When writing a commit message right after addressing
PR review comments, describe the concrete change (e.g. "extract yaml
lookups into a named helper, move test fixtures to files") — never
"address review", "apply feedback", "fix comments", etc. Applies
across every repo, not just YnabSharp.

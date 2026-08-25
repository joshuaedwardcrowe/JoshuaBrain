---
name: feedback-no-unrequested-deviation
description: "When changing existing code, deviate only where the change requires it — no renames, no helper extractions, no abstractions the task didn't ask for"
metadata: 
  node_type: memory
  type: feedback
  originSessionId: 0754a3df-faa9-4e86-a35e-078f88fc349c
  modified: 2026-08-25T23:34:00.907Z
---

Fixing or extending existing code means changing only what the change
requires. Renaming a method, extracting helpers, or introducing a seam
that nobody asked for is a deviation to be justified, not a free
improvement. When the code had a shape before, resemble that shape.

**Why:** On KitCli #167 (2026-08-26) a one-shot invocation dropped the
chained steps of a run. The fix needed the host loop to exist once instead
of twice. Around that minimal change I renamed `ExecuteRunOperation` to
`RunAsk` — "a deviation I did not ask for" — extracted `Complete`,
`HasQueuedStep`, `StartSession` and `EndSession`, and invented three
successive abstractions for "where an ask comes from" (`SourceAsk`, then a
base-class default, then an `ArgsCliIo`). Each was rejected in turn:
"you're getting caught because you're trying to bind TerminalCliApp to
Io.Ask", "I hate ArgsCliIo, you dont need it", "its still leaking". The
answer was already on the base class. The calibration that unstuck it was
the user asking to see the file as it looked before the split it was
fixing.

**How to apply:** Before restructuring existing code, pull up its previous
shape — `git log --oneline -- <file>` then `git show <commit>^:<file>` —
and treat that as the target to resemble. Keep existing member names
through a signature change. Account for every added member: if it exists
to remove duplication *you* introduced, remove the duplication instead.
Before adding an abstraction for a varying input, check what the base type
already holds. Flag behaviour changes that ride along in a refactor rather
than letting them pass as cleanup — see
[[feedback_pr_review_response_triage]] and [[feedback_default_to_brevity]].

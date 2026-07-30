---
name: feedback-pr-review-response-triage
description: Triage PR review comments into fix/question/out-of-scope-idea and share the triage before editing any files
metadata: 
  node_type: memory
  type: feedback
  originSessionId: 8ca57252-6b27-4f26-9743-8937583c0505
  modified: 2026-07-30T20:34:25.385Z
---

When responding to a batch of PR review comments, don't open the editor first. Triage every comment into one of three buckets, then share that triage with the user for agreement *before* touching any files:

1. **Mechanical fixes with clear precedent** — style/nit comments where the codebase already has an established pattern to point to (e.g. matching an existing sibling file's convention).
2. **Direct questions aimed at the reviewer/assistant** — phrased as a question ("where's the doc comment?", "what does X represent?") that want an answer on the thread, not necessarily a code change.
3. **Design decisions or out-of-scope ideas** — anything that changes the shape of something beyond the PR's stated scope (e.g. "should this get a Connected-style wrapper?"). These aren't unilateral calls — surface them, and where a repo's own CONTRIBUTING/CLAUDE.md already says "file it as its own issue," follow that instead of deciding inline.

**Scope test for bucket 3, specifically:** "out of scope" means code the current PR doesn't touch, not "code similar to a broader pattern." If a comment flags a gap in a file/method the PR itself introduces or edits, that part is in-scope and gets fixed directly in the PR — only the part touching pre-existing, untouched code gets filed as a separate issue. A single comment can split across both: fix the piece inside the diff, ticket the piece outside it. Watch for a reviewer explicitly drawing that line (e.g. "file a ticket for the others, but don't leave *this one* like this") — that phrasing is telling you the comment isn't purely bucket 3.

**Why:** Caught 2026-07-30 on YnabSharp PR#109 — given a batch of 13 review comments, jumped straight into editing files, including quietly treating a genuine design question ("do you need a ConnectedPayee?") the same as a mechanical style nitpick, and made an edit before the user had a chance to weigh in. The user's objection: reacting to review feedback is a different task from writing code off an agreed plan — comments carry different intents, and conflating them by silently "fixing" everything skips a human decision point that was the entire reason review exists. A second, sharper miss followed on the same PR: a comment said the missing doc-comment convention should be backfilled onto *pre-existing* clients via a ticket, but that *this PR's own* `PayeeClient.GetAll()` should not ship in the same undocumented state — that got flattened into "file one ticket for all of it," skipping the actual fix the PR itself owed. The repo's own `repo-operating-model` skill already states the correct order: fix first, then reply describing the fix — don't file-and-reply without checking whether part of the ask was actually in-scope.

**How to apply:** Whenever asked to look at or respond to PR review comments (after finding all of them per [[feedback_pr_comment_audit]]), produce the three-bucket triage as a message first, applying the scope test above per-comment rather than per-batch. Only start editing after the user agrees with the triage. Reply to every comment thread individually once resolved — including the ones that get an answer instead of a code change — never leave a thread silently unaddressed. This applies in any repo; a repo's own CLAUDE.md/CONTRIBUTING.md rule for bucket 3 (e.g. "offer to file it as its own issue") takes precedence over guessing.

---
name: feedback-no-unrequested-github-actions
description: "A chat statement about implementation preference or design scope is not a request to post or edit anything on GitHub — only act there when explicitly asked to"
metadata:
  node_type: memory
  type: feedback
  modified: 2026-10-10T05:30:00.000Z
---

Don't post, edit, or otherwise touch a GitHub issue/PR/comment off the back of a chat statement about implementation direction, scope, or preference — even one phrased as a correction, even on a comment Claude itself posted minutes earlier.

**Why:** Caught 2026-10-10 on KitCli#299. The user said "For the implementation today, I wouldn't even use the abstraction for an enum, just roll our own enum" — a design preference continuing the #299 proposal discussion in chat. Claude read this as a cue to immediately edit a live, already-posted GitHub comment to match, without asking. The user's objection wasn't that the edit was factually wrong — it was that no GitHub action was called for at all; it was still a chat-level design conversation. Comments on a shared issue are visible to others, same category as PRs and merges.

**How to apply:** Treat "I'd do X differently" / "let's not use Y" / scope clarifications as input to the next thing Claude *says*, not the next thing it *posts*. Only create, edit, or comment on GitHub content when the user's message is itself a request to do so ("post that", "comment that on the issue", "open the PR"). If an already-posted comment looks stale after a design pivot, say so in chat and ask whether to update it — don't silently re-edit shared content to stay consistent.

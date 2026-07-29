---
name: feedback-joshuabrain-push-policy
description: "After any meaningful memory write/edit, commit and push to the JoshuaBrain repo immediately - not periodic"
metadata: 
  node_type: memory
  type: feedback
  originSessionId: 681f9a31-eb28-4ccf-8913-2eb0f7bd2929
  modified: 2026-07-29T22:42:30.167Z
---

Whenever a memory file (`MEMORY.md` or an individual typed file in the memory directory) is written or meaningfully edited, immediately commit and push that change to [github.com/joshuaedwardcrowe/JoshuaBrain](https://github.com/joshuaedwardcrowe/JoshuaBrain) in the same turn, rather than leaving it to accumulate uncommitted or batching pushes periodically.

**Why:** The user asked how memory updates should sync to JoshuaBrain after it was created (2026-07-29). JoshuaBrain's entire value is backup/insurance against local-machine loss plus a real version history — that only works if it stays current. Letting changes accumulate uncommitted defeats the purpose the same way an unbacked-up backup does.

**How to apply:** After any `Write`/`Edit` to a file in the memory directory (including `MEMORY.md` itself), run `git add -A && git commit -m "..." && git push` in that directory before moving on, unless the user has explicitly asked to batch changes for some reason in that specific session.

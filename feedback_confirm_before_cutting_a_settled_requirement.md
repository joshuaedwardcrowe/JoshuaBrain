---
name: feedback_confirm_before_cutting_a_settled_requirement
description: "A terse instruction that could be read as dropping an already-settled requirement needs confirming before acting on it, not guessing"
metadata:
  node_type: memory
  type: feedback
  originSessionId: unknown
  modified: 2026-10-11T00:00:00.000Z
---

When a requirement has been established as load-bearing across many turns — stated explicitly at the start, re-confirmed more than once — a later one-word instruction that *could* be read as cutting it ("Simplify.") needs a confirming question before acting, not a guess followed by deletions.

**Why:** Flagged 2026-10-11 on KitCli's sub-command-fallback investigation (#289 / investigation 0011). The user's first message in the whole thread stated the requirement explicitly: an uncovered sibling command (`/hello mate`) must resolve with zero hand-written code. That stayed true across many turns of design discussion. When the user later said "Simplify." in response to a breakdown of which parts of the implementation were load-bearing versus risky, it was read as "cut the risky part" — which happened to be the exact mechanism satisfying that original, never-retracted requirement. Deleted a file and rewrote the registration logic before confirming, then had to be asked "in what world is this correct?" The right move was to ask which of the two readings was meant *before* touching any files, the same way earlier ambiguous instructions in the same session ("fallback only when there isn't a declared factory", "laymen's terms") had already been gotten wrong by guessing first.

**How to apply:** Before acting on a short, ambiguous instruction, check it against requirements already settled earlier in the conversation. If the instruction could be satisfied in a way that silently drops one of them, ask which reading is meant before writing or deleting anything — especially after the same kind of guess has already cost a redo once in the same session.

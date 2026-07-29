---
name: feedback-permission-prompts
description: "How to handle Bash commands that trigger a permission prompt because they're not covered by an existing allow rule"
metadata: 
  node_type: memory
  type: feedback
  originSessionId: 6b43d49e-e64e-4080-bcac-bbade7e66b13
  modified: 2026-07-25T21:56:20.524Z
---

When a command triggers a permission prompt for work happening inside
one of the user's own repositories, don't just get it approved once and
move on — raise whether it's worth adding a permanent rule to
`~/.claude/settings.json` (`permissions.allow`) so the same shape of
command doesn't keep prompting in future sessions.

**Why:** the user doesn't want to keep manually approving the same kind
of command repeatedly. They're fine with repo-internal operations
(git/gh/dotnet and similar) "just working" going forward. They only want
to be asked to think it through case-by-case for things that are
genuinely one-off, risky, or reach outside the repository (e.g. a novel
external API call, something destructive, a new domain to WebFetch).

**How to apply:**
- Before proposing a new allow rule, check whether the prompt actually
  came from a missing rule at all — `Bash` allow rules match on the
  command's literal text *prefix*, not on cwd/directory. A command like
  `cd /path && git ...` or a `for`/`cat` pipeline won't match an existing
  `Bash(git *)` rule even though it's "basically git" — the fix there is
  to phrase the command so it matches what's already allowed (e.g.
  `git -C /path ...` instead of `cd /path && git ...`), not to add a new
  rule.
- Only when there's a genuine gap (a repo-internal command shape that's
  reasonably going to recur and isn't covered), surface it and ask if
  the user wants it added permanently.
- Keep this scoped to repository work. Don't extend the same "just
  allow it" instinct to actions outside a repo, or to destructive/
  high-blast-radius actions — those still warrant asking each time per
  the standing risk-based confirmation rules.

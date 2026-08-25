---
name: feedback_search_issues_before_proposing
description: "Search existing issues before proposing work or picking a doc type — the repo often already frames it, and that framing decides the deliverable"
metadata:
  type: feedback
---

Before proposing a design or choosing which doc type to write, search the repo's open issues for the topic. The existing framing decides the deliverable.

KitCli#135 ("Release tooling may not respect SemVer — needs checking before deciding whether there is a real bug") had framed the semver question as a spike the whole time. A whole design was proposed in chat and filed as an ADR before that issue was found; the correct deliverable was an **investigation** answering #135, with the ADR as the decision it justifies (2026-08-25).

**Why:** A spike issue that already exists sets the doc type, the verdict format, and whether the parent stays open — see [[feedback_spike_outcome_rule]]. Proposing into a vacuum reinvents framing that is already agreed.

**How to apply:** `gh issue list --search "<topic> in:title" --state all` before writing a design doc or opening a PR that files one. Relates to [[feedback_check_pr_conventions_before_opening]] — same instinct, applied to the route rather than the format.

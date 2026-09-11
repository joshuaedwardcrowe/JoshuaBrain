---
name: feedback_issue_problem_must_be_true
description: "An issue's Problem section must be verified against the code and must say why the reader cares — never assert a capability is missing without checking the workaround"
metadata:
  type: feedback
---

Before filing an issue, prove the Problem section against the source, the same way a doc's names and signatures get verified. Then state what the reader loses today, in their own terms.

Six KitCli issues (#254-#259, 2026-09-11) were filed claiming capabilities were missing. Four overstated it and one was simply wrong: #255 said a command could not ask the person a question, when a handler injects `ICliIo` and calls `AskAsync` — a pattern the repo's own user guides already show. The real gap was narrower: the answer comes back as a raw line, so yes/no, pick-from-a-list, hidden entry and re-ask-until-valid are hand-written every time. The user's reaction to the rest was "and? why do I care?".

**Why:** An issue that overstates gets discovered as false by whoever picks it up, and the whole ticket loses trust. "You cannot do X" is a much stronger claim than "X costs you Y every time", and is usually the false one — a framework with a replaceable seam nearly always has a workaround.

**How to apply:** Every Problem section carries a **What you can do today** paragraph naming the workaround and its real cost. Open the file and check the claim before writing it down. Lead with what someone using the thing experiences, not with which method takes which type. Relates to [[feedback_default_to_brevity]] and [[feedback_search_issues_before_proposing]].

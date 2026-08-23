---
name: feedback_no_process_without_a_consumer
description: "Before requiring a process artifact — velocity, iterations, a report, a board field — name the decision it feeds and who makes it; no consumer, don't add it"
metadata: 
  node_type: memory
  type: feedback
  originSessionId: a94b8a33-12ae-450e-8ceb-ea3d391fa209
  modified: 2026-08-23T21:12:14.000Z
---

Before requiring any process artifact — a velocity figure, fixed-length iterations, a recurring report, a new board field, a status gate — name the specific decision it feeds and who makes it. If that can't be named, don't add it, and don't frame existing work as incomplete without it.

**Why:** 2026-08-23, KitCli backlog calibration. After sizing 49 issues I asserted the 172 points were meaningless without velocity, put "— velocity" in a summary as a missing figure, and made "what is an iteration here?" the question that "decides whether the rest survives." Joshua answered it, then asked why we needed to know. We didn't. Velocity exists to forecast a date or size an iteration's capacity; a solo repo with no deadline and nobody waiting has neither consumer. Relative sizing — this issue is a bigger bite than that one — is the entire value of the estimates and needs no velocity data ever. I had imported a staffed-team practice, manufactured a requirement from it, and then spent four turns debating where to put tooling for a metric with no consumer and no data (zero estimated issues had ever closed).

The tell was available early and ignored: I wrote "no velocity, so no time forecast" as a *gap* rather than asking whether a forecast was wanted.

**How to apply:** Complete this sentence before proposing the artifact — "this feeds `<decision>`, made by `<who>`, at `<when>`." If it won't complete, drop it. Applies with extra force to anything carrying Jira/Scrum vocabulary — velocity, burndown, capacity, sprint, iteration — because those words arrive with an implied staffed team, deadline, and stakeholder that may not exist here. Ask whether each is actually present rather than assuming the surrounding machinery.

Note this cuts against step 6 of [[methodology_engineering_estimation_pipeline]] ("fixed-length iterations + end-of-iteration review"), which is the same import and has never once run in any repo that documents it. Re-examine it rather than defending it. Related: [[methodology_documentation_effort_ceiling]] — don't document more than you do.

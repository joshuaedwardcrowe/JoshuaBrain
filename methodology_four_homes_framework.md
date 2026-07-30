---
name: methodology-four-homes-framework
description: "The four homes for deciding where any piece of process/knowledge should live - CAIRN, SoloCAIRN, JoshuaBrain, or a specific repo's own CONTRIBUTING.md"
metadata: 
  node_type: memory
  type: feedback
  subtype: methodology
  originSessionId: 681f9a31-eb28-4ccf-8913-2eb0f7bd2929
  modified: 2026-07-30T21:16:57.685Z
---

When deciding where a piece of process, convention, or knowledge should be written down, there are four distinct homes, not a blur between "personal" and "shared":

1. **CAIRN** (upstream, Abdullah Siddique's) — universal to *any staffed team*, not solo-specific.
2. **SoloCAIRN** (the fork) — universal to *any solo maintainer* doing AI-assisted work, not specific to Joshua's own taste.
3. **JoshuaBrain** — Joshua's own personal preferences and working style. Not binding on anyone else, including other contributors to his own repos.
4. **Each individual repo's own `CONTRIBUTING.md`** — the actual binding, shared contract for anyone (including Joshua) contributing to that specific repo. This applies per-repo, not per-"ecosystem" — and orgs meant to operate as independent simulated organizations (KitCli, Diagnosea) get their *own* infrastructure (their own Ideas board, their own CONTRIBUTING.md) rather than sharing Joshua's personal-account one, even though Joshua owns/runs them. Repos under Joshua's own personal account that aren't simulated orgs (SpendfulnessCli, YnabSharp) can reasonably share personal-account infrastructure like the Ideas board.

**The test for each:** would this apply to any team, anywhere (→ CAIRN)? Any solo maintainer, not just Joshua (→ SoloCAIRN)? Is it genuinely just how Joshua personally likes to work, not something another contributor needs to follow (→ JoshuaBrain)? Does it need to be binding for anyone contributing to *this specific repo/org* (→ that repo's own CONTRIBUTING.md, and if the org is a simulated independent organization, its own boards/infra too, not Joshua's personal ones)?

Surfaced across several corrections in one session (2026-07-29/30): a "GitHub Issues as story artifact" decision nearly got written into SoloCAIRN itself (wrong — it's per-repo, not universal to all solo maintainers) and nearly left only in JoshuaBrain (also wrong — other contributors don't read that). A "KitCli idea" nearly ended up on Joshua's personal Ideas board (wrong — KitCli is a simulated independent org and needed its own board, since it's owned by the KitCli org, not Joshua personally). Each mistake was the same shape: collapsing two of the four homes into one.

The exact same shape recurred even with this memory already on file (2026-07-30, YnabSharp#109/PR#115): "PRs should mirror their linked issue's labels/milestone" was reasoned as "this should be consistent across repos" → "therefore SoloCAIRN," skipping the four-way test itself. SoloCAIRN's own `10-what-cairn-does-not-solve.md` explicitly disclaims "conventions and standards" as out of scope (it owns the feature-build artifact pipeline, not general repo hygiene) — the correct home was [[methodology_pr_mirrors_issue_metadata]], a personal cross-repo habit applied individually into each repo's `CONTRIBUTING.md`, the same shape as [[methodology_pr_size_limit]]. Having this memory did not prevent the mistake; only actually re-reading SoloCAIRN's scope docs did.

**How to apply:** Before writing any process/convention down, explicitly run it through the four-way test above rather than defaulting to "put it wherever feels closest." When in doubt, it's worth surfacing the ambiguity out loud rather than picking one silently — several of the corrections above only happened because the user caught a wrong placement after the fact, not because the test was applied up front. This memory file itself is an instance of the pattern: it and five siblings were originally filed as `feedback` (reactive correction) when they were really `methodology` (stated practice) — see the `subtype` field this and similar files now carry.

Two cheap, mechanical tripwires catch most misses without re-deriving the four-way test from scratch each time (added 2026-07-30, after a feature idea got saved to memory instead of the GitHub Ideas board, and two new `methodology_*` files got typed `project` instead of `feedback`/`methodology`):

- **Naming/type mismatch**: a file named `methodology_*` must carry `type: feedback` + `subtype: methodology`. If the filename and the metadata type disagree, stop and recheck — don't let the filename get chosen from one line of reasoning and the type from another.
- **"Is this real work yet?" check**: if the content describes an idea, feature, or task that isn't yet WAG'd/scoped, it belongs on a GitHub Ideas board as an issue (see [[feedback_idea_routing]]), not in JoshuaBrain at all — memory is for durable context about how Joshua works, not a parking lot for backlog items.
- **"Consistent across repos" is not the SoloCAIRN test**: wanting the same rule in every repo does not by itself mean SoloCAIRN is the right home — that's true of most JoshuaBrain `methodology_*` entries too. Before proposing an addition to SoloCAIRN specifically, actually re-read `docs/10-what-cairn-does-not-solve.md` and `docs/02-philosophy.md` in that repo rather than reasoning from the general shape of the rule.

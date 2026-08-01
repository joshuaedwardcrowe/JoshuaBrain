---
name: project-spendfulnesscli-reorganisation-usecase
description: "Bulk reorganisation of budget categories, groups, and transactions is a first-class SpendfulnessCli goal, driven by the user re-shuffling their own budget every couple of years"
metadata: 
  node_type: memory
  type: project
  originSessionId: 5be4966d-ae44-42f4-b84a-b40648b25c41
  modified: 2026-08-01T08:31:16.735Z
---

The user re-shuffles their own YNAB budget structure roughly every couple of years — renaming/merging/moving categories and category groups, and re-assigning the transactions that hang off them. Because of that, **reorganising** budget categories, groups, and transactions is a milestone-level goal for SpendfulnessCli, not a nice-to-have. Stated 2026-08-01.

**Why:** This is a recurring personal workflow, not a one-off migration, so the CLI needs it to be repeatable and safe (re-runnable, previewable) rather than a throwaway script. It also has teeth for [[project-spendfulnesscli-mission]]: re-shuffling categories is how the four-axis spendfulness taxonomy actually gets applied to an existing budget, so reorganisation is the mechanism by which the mission lands on real data.

**How to apply:** When scoping or prioritising work in this repo, treat bulk category/group/transaction re-assignment as a target capability and check whether a proposed change helps or blocks it. Note that as of 2026-08-01 no GitHub milestone carries this name — the nearest is "Modifying YNAB Data" (#3), whose issues are about splits, sanitizing, and naming schemes rather than bulk re-org. Confirm with the user which milestone this belongs to before filing issues against one.

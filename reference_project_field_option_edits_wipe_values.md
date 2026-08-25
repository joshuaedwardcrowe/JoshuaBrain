---
name: reference_project_field_option_edits_wipe_values
description: "GitHub's updateProjectV2Field regenerates every single-select option id and blanks every item's value; recover the old values from ProjectV2ItemStatusChangedEvent timeline entries"
metadata:
  node_type: memory
  type: reference
  modified: 2026-08-25T19:30:00.000Z
---

`updateProjectV2Field` with `singleSelectOptions` **replaces the option set wholesale**. Even when every existing option is resent byte-identical (same name, colour, description), GitHub mints **new option ids** for all of them, and every project item's value for that field is orphaned — the whole board reads `(empty)`. There is no `addSingleSelectOption` mutation and no undo.

**Before touching a single-select field on a populated board**, snapshot the current values:

```graphql
{ organization(login: "…") { projectV2(number: 6) { items(first: 100) { nodes {
  id content { ... on Issue { number } }
  fieldValueByName(name: "Status") { ... on ProjectV2ItemFieldSingleSelectValue { name optionId } } } } } } }
```

**Recovery if you skipped the snapshot:** the values are reconstructible from issue timelines. `ProjectV2ItemStatusChangedEvent` carries `createdAt`, `previousStatus`, `status` and `project { number }` — the latest event per (issue, project) is the value that was wiped. It survives the wipe because it lives on the issue, not the field.

```graphql
i147: issue(number: 147) { timelineItems(first: 100, itemTypes: [PROJECT_V2_ITEM_STATUS_CHANGED_EVENT]) {
  nodes { ... on ProjectV2ItemStatusChangedEvent { createdAt previousStatus status project { number } } } } }
```

Then restore with batched `updateProjectV2ItemFieldValue` aliases against the **new** option ids, per [[feedback_batch_github_project_writes]]. This only covers the `Status` field — there is no equivalent timeline event for other single-selects such as `Priority`, so for those the pre-flight snapshot is the only safety net.

**Why:** 2026-08-25, adding a `Not Required` option to the Status field on KitCli's seven delivery boards ([[methodology_traditional_project_board_layout]]) blanked all 67 items in one mutation. Full recovery from timelines took three queries; without `ProjectV2ItemStatusChangedEvent` the board state would have been unrecoverable.

---
name: feedback_chart_numbers_over_tables
description: Show comparative numbers as a mermaid chart, not a table or prose
metadata:
  type: feedback
---

Show numbers that compare as a mermaid `xychart-beta` bar chart, not as a table or as prose. Keep prose for what a chart cannot carry, such as methodology and caveats.

**Why:** On 2026-10-17, KitCli review 0003 (development pace) first gave its before/after figures as a table. Offered a bar chart instead, the user said: "Boom! I'd prefer that over tables or prose really."

**How to apply:** One chart per measure, with a plain label on each bar ("February", "July to October") and one unit per chart. `xychart-beta` has no key and cannot stack or group bars, so a single chart mixing measures or units ("Code Feb", "Tests now", "PRs merged before") reads as "confusing ass graphs". Both GitHub and the docfx modern template draw it. Related: [[feedback_group_by_the_unit_that_changes]], [[feedback_default_to_brevity]].

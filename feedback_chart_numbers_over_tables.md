---
name: feedback_chart_numbers_over_tables
description: Show comparative numbers as a mermaid chart, not a table or prose
metadata:
  type: feedback
---

Show numbers that compare as a mermaid `xychart-beta` bar chart, not as a table or as prose. Keep prose for what a chart cannot carry, such as methodology and caveats.

**Why:** On 2026-10-17, KitCli review 0003 (development pace) first gave its before/after figures as a table. Offered a bar chart instead, the user said: "Boom! I'd prefer that over tables or prose really."

**How to apply:** `xychart-beta` cannot stack bars or show a key, so put one bar series on the chart and label each bar with both its group and its period ("Code Feb", "Code Jul-Oct"). Both GitHub and the docfx modern template draw it. Related: [[feedback_group_by_the_unit_that_changes]], [[feedback_default_to_brevity]].

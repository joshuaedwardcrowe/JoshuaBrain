---
name: feedback_group_by_the_unit_that_changes
description: Explain state across a sequence by grouping steps under the unit whose boundary matters, ideally as a diagram, not as annotated lines or a wide table
metadata:
  type: feedback
---

When explaining how state carries across a sequence of steps, group the steps under the unit whose boundary matters, and show the state at each step. A sequence diagram with one shaded `rect` block per unit works best.

**Why:** On 2026-10-15, explaining KitCli's session vs run lifetimes failed four times: a wide seven-column table, arrow-annotated lines, "← final outcome" markers, then prose. Each one left run boundaries as side annotations. Grouping the lines under "Run 1 / Run 2 …" landed straight away ("Much better"). The same shape as a mermaid `sequenceDiagram` with `rect` blocks, added to `docs/concepts/outcomes.md`, was called "significantly better than our back and forth at explaining".

**How to apply:** If a reader must track which group each step belongs to, make the group the structure: a heading per group, or a `rect` block per group in mermaid. Show only the values that change. Reach for this before a table or a list of annotated lines. Related: [[feedback_default_to_brevity]].

---
name: feedback_cairn_docs_terse_register
description: "CAIRN/SoloCAIRN docs are light-touch — short declarative sentences, no re-explaining context a nearby paragraph already covers. Match that register, don't default to explanatory prose."
metadata: 
  node_type: memory
  type: feedback
  originSessionId: 9c6b45a7-a253-4f6b-a0fa-ac50bd7f8c3d
  modified: 2026-08-05T14:30:36.130Z
---

CAIRN and SoloCAIRN's docs use a deliberately terse register: short declarative sentences, minimal subordination, and no restating context a nearby paragraph already established. When adding text to these docs, edit the smallest possible span of an existing sentence rather than appending new sentences or paragraphs that re-explain rationale already present nearby — even when the new point feels like it deserves its own space.

**Why:** Corrected 2026-08-05 across two rounds on [SoloCAIRN PR#21](https://github.com/joshuaedwardcrowe/SoloCAIRN/pull/21). First draft added three new sentences restating the pair/no-pair rationale the two paragraphs directly above it already covered. The "tightened" second attempt was still noticeably longer than the doc's own baseline register — e.g. `03-lifecycle.md`'s Discovery "Done when" line is a single clause, no subordination. The fix that actually landed was a near word-for-word swap on the existing sentence, not new structure at all.

**How to apply:** Before proposing text for a CAIRN/SoloCAIRN doc, read a comparable definition-style line nearby (a "Done when," a table row, a short rule) and match its sentence length and clause count before drafting. Default to editing an existing sentence over adding a new one. If a correction is needed after landing something, cut rather than rephrase-and-shorten — the second draft repeated the mistake at a smaller scale instead of changing approach.

---
name: feedback-test-code-conventions
description: "Testing-code style preferences that apply across every repository, not just one project"
metadata: 
  node_type: memory
  type: feedback
  originSessionId: 8121d6e0-09a8-4ea6-827a-4c20a4a8d259
  modified: 2026-07-26T23:36:49.199Z
---

Three conventions for test code, wanted across every repository, not
just the one they were first raised in ([[feedback_pr_size_limit]] is
the other cross-repo standing rule):

- **Build test doubles reusably from the start, not as a private nested
  class promoted later.** If a sibling class carries a
  `// TODO: Write unit tests.` marker (or similar), that's a signal more
  tests of the same shape are coming — put the double in a shared
  test-helpers location the first time, not the second.
- **Serialize real DTOs instead of hand-writing JSON/data string
  literals** for canned fixture bodies. Construct the actual
  response/request type and serialize it, rather than typing out the
  wire format by hand — the fixture can't drift from the real shape,
  and a property rename breaks the build instead of silently
  invalidating the test.
- **Name test doubles `Test*`**, not `Stub*`/`Fake*`/`Mock*`.

**Why:** raised via PR review comments on YnabSharp #68. All three were
things I could have applied on the first pass without needing a written
rule — the signals (sibling `TODO: Write unit tests.` markers, the real
DTO types already in hand from the same task) were already visible — so
treat these as defaults to apply proactively, not just react to when
reviewed.

**How to apply:** apply by default when writing test code in any repo,
even where no local CONTRIBUTING.md/style doc mentions it. For a repo
that has its own contributing doc (e.g. YnabSharp's "Testing" section in
`CONTRIBUTING.md`), that doc is the source of truth if it ever
diverges from this — but absent one, use these defaults.

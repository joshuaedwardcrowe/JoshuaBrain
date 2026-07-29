---
name: methodology-test-code-conventions
description: "Testing-code style preferences that apply across every repository, not just one project"
metadata: 
  node_type: memory
  type: feedback
  subtype: methodology
  originSessionId: 681f9a31-eb28-4ccf-8913-2eb0f7bd2929
  modified: 2026-07-29T23:28:32.112Z
---

Three conventions for test code, applied across every repository, not
just the one they were first raised in ([[methodology_pr_size_limit]]
is the other cross-repo standing rule):

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

Apply these proactively by default when writing test code in any repo,
even where no local `CONTRIBUTING.md`/style doc mentions them — the
signals that justify each rule (sibling `TODO: Write unit tests.`
markers, real DTO types already in hand from the same task) are usually
already visible before anyone has to point them out.

**How to apply:** use these as defaults in any repo. For a repo that
has its own contributing doc (e.g. YnabSharp's "Testing" section in
`CONTRIBUTING.md`), that doc is the source of truth if it ever diverges
from this — but absent one, use these defaults.

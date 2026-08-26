# Changing code

Full reasoning: the named files in `~/.claude/projects/-Users-joshuacrowe/memory/`.

- **Change only what the change requires.** A rename, an extracted helper or a new
  abstraction nobody asked for is a deviation to justify. Pull up the previous shape —
  `git log --oneline -- <file>`, `git show <commit>^:<file>` — and resemble it. Keep
  existing member names through a signature change. Before abstracting a varying input,
  check what the base type already holds. (`feedback_no_unrequested_deviation`)
- **Never write a `//` comment explaining why.** Put it in a name — a local, a private
  method, a test name — or in a `///` doc comment above the class, record or method.
  Existing `// TODO:` markers stay. (`feedback_names_over_why_comments`)
- **Test doubles are reusable from the first test**, one file per double, named `Test*`,
  in a shared test-helpers location — not a private nested class promoted later.
  Serialize real DTOs rather than hand-written JSON. (`methodology_test_code_conventions`)
- **Flag a behaviour change riding along in a refactor** rather than letting it pass as
  cleanup.

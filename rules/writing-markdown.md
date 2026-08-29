# Writing markdown

Each repo's `CONTRIBUTING.md` is binding and more specific than this. Read it.
Full reasoning: `~/.claude/projects/-Users-joshuacrowe/memory/feedback_default_to_brevity.md`.

## Prose

- **Strunk.** Active voice. Short declarative sentences. Omit needless words.
  Positive form — say what a thing does, not what it does not do.
- **Laymen's terms.** Say what a reader can now do. Name a type only when they
  have to type it. Explain the problem before asserting things about it.
  This covers tickets, and outranks resembling a dense sibling artifact —
  the sibling is the thing off-style.
- **Lead with the answer**, rather than building to it. Never append a Q&A that
  re-answers the body.
- **Dense is not clear.** Cut words, never the connective tissue that makes a
  claim followable. An unreadable page lands nothing.
- **Anchor it.** Inline the real file path, route, type name or code described.
- **Name the sharp edge in one sentence** — "the cost is zero durability" — and
  say plainly what is not built yet.
- **If it is flagged as too long, delete.** Do not rephrase-and-shorten.
- **Abstract the examples** in a doc teaching a reusable approach. Never the
  user's real personal details.

## Which doc

| Kind | Holds | Sections |
| --- | --- | --- |
| ADR | a decision, its alternatives, its consequences | Context / Decision / Alternatives considered / Consequences |
| Concept | how a subsystem works today | Premise / Problem / Solution / Constraints & tradeoffs / Related concepts |
| Investigation | what a spike found, verdict first | Verdict / Recommendation / What was established / Evidence / Open questions / Out of scope |
| User guide | how to do a task, black-box | Before you start / Walkthrough / What's real today / Related docs |

Write an ADR for a cross-cutting pattern, a project or package boundary change, a
breaking change to public API shape, or reversing an earlier ADR. Skip it for bug
fixes, internal refactors, and anything a code comment covers. When unsure, don't.

A user guide shows *how* without the machinery; the concept doc explains *why*. A
guide reaching for an internal reason links the concept doc instead.

## Shape

- **Copy the folder's `0000-template.md`** and follow a sibling's skeleton exactly.
- **Number every doc sequentially** — `000x-topic-in-kebab-case.md`, titled
  `# 000x. Title` — whatever the kind, in the order a reader should meet them.
- **Under 60 lines.** Past 100 the doc holds two concepts, or reference material
  belonging in source XML docs. Each section is one to three short paragraphs;
  alternatives, tradeoffs and consequences are one-line bullets, reason inline.
- **Verify every name, signature, sample and transcript against source** before
  writing it down. A doc that does not match `main` is worse than no doc.
- **Keep it current in the same PR** that makes it inaccurate.
- User guides and READMEs are second person, present tense. Concept docs and ADRs
  describe the code in the present tense.
- A README is longer and fixed: Table of Contents / Purpose / Getting Started
  (Prerequisites, Installation & Set-up, Building & Usage) / The Core Idea /
  Project Structure / Testing / Further Documentation / Support. Getting Started is
  copy-pasteable commands; The Core Idea is a real transcript, not a description.

## Adding a doc or a convention

- **Don't document more than you do.** Reach for the lightest mechanism that already
  works — propose in chat, then create — before adding a doc type, a folder or a
  PR-reviewed convention. (`methodology_documentation_effort_ceiling`)
- **Restating a rule that was already written does not enforce it.** If work broke a
  documented convention, the failure was reading it. Revert the addition, say the rule
  already covered it, and propose a mechanism — a CI check, a template field — if the
  miss is worth preventing. Add wording only when the rule genuinely wasn't there.

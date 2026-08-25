---
name: feedback_names_over_why_comments
description: "Never write a 'why' comment inline — put it in a name, or in a documentation comment above the type or method"
metadata:
  node_type: memory
  type: feedback
  modified: 2026-08-25T22:10:00.000Z
---

Code should be self-documenting. When about to write a comment explaining *why* a line is there, first try to put the explanation in a **name** — a local variable, a private method, or the test name. A name travels with the code, cannot drift from it, and is read by everyone who reads the line.

```csharp
// Assert - TCommand is constrained to CliCommand and nothing more. A new() constraint would
// exclude exactly the commands this overload exists for: the ones with constructor arguments.
Assert.That(typeof(TestParameterisedNextCliCommand).GetConstructor(Type.EmptyTypes), Is.Null);
```

becomes

```csharp
var commandTypeOnlyAFactoryCanBuild = typeof(TestParameterisedNextCliCommand);
var itsParameterlessConstructor = commandTypeOnlyAFactoryCanBuild.GetConstructor(Type.EmptyTypes);

Assert.That(itsParameterlessConstructor, Is.Null);
```

**Why:** 2026-08-25, KitCli PR#154 — "Code should be self documenting. Remove the comment, make the code self-documenting." Four lines of comment were doing work two names did better. Related: [[feedback_default_to_brevity]], since the first fix for too much prose is deletion, not rephrasing.

**An inline `//` explaining why should never exist.** There are two places for the explanation:

- **A name.** Ask what the thing would have to be *called* for the comment to be unnecessary, then extract a local or a method to get that name.
- **A documentation comment** — `/// <summary>` — above the class, record, method or test it describes. This is the wanted form, and where a longer explanation belongs.

Anything left over is not a code comment: a decision goes in the ADR, a rule in `CONTRIBUTING.md`, a follow-up in an issue. `// TODO:` markers already in a file are not covered by this and stay.

**How to apply:** reach for a name first, a `///` above the object second, and never a `//` in the middle of a method.

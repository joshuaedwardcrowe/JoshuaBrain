---
name: feedback_names_over_why_comments
description: "Encode a 'why' comment in a name before writing it as a comment — a named local, method or test name usually carries it"
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

**How to apply:** Before writing a `//` explaining intent, ask what the thing would have to be *called* for the comment to be unnecessary. Extract a local or a method to get that name. A comment still earns its place when it records something no name can hold — a language behaviour that surprises, an external constraint, a decision recorded elsewhere — and then it should be one line, not four. Prose that belongs to a decision goes in the ADR, not above the code.

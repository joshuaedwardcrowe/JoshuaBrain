---
name: project-kitcli-vision
description: "KitCli's intended ambition — an extensible conventions/framework platform for CLI-style apps, analogous to ASP.NET Web API or Umbraco"
metadata: 
  node_type: memory
  type: project
  originSessionId: 681f9a31-eb28-4ccf-8913-2eb0f7bd2929
  modified: 2026-07-28T18:49:44.734Z
---

KitCli (github.com/KitCli/KitCli, separate org from joshuaedwardcrowe's personal repos) is envisioned by the user as analogous to **ASP.NET Web API or Umbraco**: KitCli's Commands/Instructions/Workflow abstractions are conventions and extension points — like Web API's controllers/middleware/DI, or Umbraco's content-types/back-office/plugin sections — that concrete apps get built against. SpendfulnessCli's CLI is one such app built on those conventions; AI, Web, API, and CarPlay front-ends would be other apps built the same way. This lines up with SpendfulnessCli's existing "Reusable CLI NuGet" milestone ("the CLI libraries allow re-use, and can be moved to a separate repository and NuGet"). See [[project_spendfulnesscli_mission]] and [[project_spendfulnesscli_issue_tracking]] for related context.

**Why:** The user framed this analogy explicitly (2026-07-28) to set how KitCli's design should be judged — as a conventions/extensibility framework, not a rendering engine.

**How to apply:** When working on KitCli or on SpendfulnessCli commands that KitCli underpins, judge design decisions by whether they give downstream apps clean extension points and conventions to build against (Web API/Umbraco lens). Flag anything that leaks CLI-specific assumptions (console-formatted output, positional-arg parsing) into the core abstractions, since that would limit reuse the same way a CMS core leaking presentation-layer assumptions would limit Umbraco sites.

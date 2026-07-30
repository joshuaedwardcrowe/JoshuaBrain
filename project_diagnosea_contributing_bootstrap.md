---
name: project-diagnosea-contributing-bootstrap
description: "Diagnosea has no CONTRIBUTING.md in any repo; tracked as an idea on Diagnosea's own Ideas board, not here"
metadata: 
  node_type: memory
  type: project
  originSessionId: 681f9a31-eb28-4ccf-8913-2eb0f7bd2929
  modified: 2026-07-30T06:33:36.808Z
---

Diagnosea (org, 8 repos: `Submarine.Desktop`, `Submarine.UI`, `Submarine.Api`, `Submarine.UI.Testing`, `Submarine.Mobile`, `Submarine.UI.Components`, `Marketing.UI`, `Submarine.WebSockets`) has no `CONTRIBUTING.md` anywhere — checked directly (2026-07-29), 2 of the 8 (`Submarine.UI.Components`, `Marketing.UI`) are completely empty repos. Diagnosea has its own Ideas board (https://github.com/orgs/Diagnosea/projects/5, same field structure as KitCli's/Joshua's personal one). The bootstrap task is tracked there as **8 separate repo-scoped issues**, not one org-wide issue and not in this memory (see [[feedback_idea_routing]]): [Submarine.Api#191](https://github.com/Diagnosea/Submarine.Api/issues/191), [Submarine.Desktop#2](https://github.com/Diagnosea/Submarine.Desktop/issues/2), [Submarine.UI#16](https://github.com/Diagnosea/Submarine.UI/issues/16), [Submarine.UI.Testing#1](https://github.com/Diagnosea/Submarine.UI.Testing/issues/1), [Submarine.Mobile#5](https://github.com/Diagnosea/Submarine.Mobile/issues/5), [Submarine.WebSockets#2](https://github.com/Diagnosea/Submarine.WebSockets/issues/2), [Submarine.UI.Components#1](https://github.com/Diagnosea/Submarine.UI.Components/issues/1), [Marketing.UI#1](https://github.com/Diagnosea/Marketing.UI/issues/1).

**Why:** Surfaced while auditing what a "SoloCAIRN pipeline" (points, PR conventions, story-artifact choice) should look like for a repo that doesn't have any process documented yet at all — Diagnosea was the concrete example. Split into one issue per repo (2026-07-30) rather than one org-wide issue, because each repo's actual gaps differ (e.g. Submarine.Api already has a rich effort/status label scheme; Submarine.Mobile has only a single `POC` label; the two empty repos have nothing to assess yet). The durable fact worth keeping here is the *pitfall*, not the task: don't assume Diagnosea needs the exact same conventions as KitCli/YnabSharp/SpendfulnessCli (see [[methodology_four_homes_framework]] on not over-applying one repo's specifics elsewhere) — it's a different stack per repo (Electron desktop app, REST API, mobile, WebSockets, UI, e2e tests).

**How to apply:** If asked to help with Diagnosea's CONTRIBUTING.md work, check the relevant repo's issue above and the Ideas board for current status first rather than assuming it hasn't started. Whenever a repo is worked, read that repo's actual code/structure first — the way SpendfulnessCli's `CONTRIBUTING.md` was written from its real ADR/CONCEPTS.md layout rather than copied from KitCli's or from another Diagnosea repo.

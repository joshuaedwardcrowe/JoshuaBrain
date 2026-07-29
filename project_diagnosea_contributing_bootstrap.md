---
name: project-diagnosea-contributing-bootstrap
description: "Diagnosea's repos need CONTRIBUTING.md bootstrapped from scratch - not started yet"
metadata: 
  node_type: memory
  type: project
  originSessionId: 681f9a31-eb28-4ccf-8913-2eb0f7bd2929
  modified: 2026-07-29T23:51:01.684Z
---

Diagnosea (org, 8 repos: `Submarine.Desktop`, `Submarine.UI`, `Submarine.Api`, `Submarine.UI.Testing`, `Submarine.Mobile`, `Submarine.UI.Components`, `Marketing.UI`, `Submarine.WebSockets`) has no `CONTRIBUTING.md` anywhere — checked directly (2026-07-29), 6 repos have none, 2 (`Submarine.UI.Components`, `Marketing.UI`) are completely empty repos.

An Ideas board exists for Diagnosea (https://github.com/orgs/Diagnosea/projects/5, same field structure as KitCli's), but the `CONTRIBUTING.md` bootstrap itself hasn't started — it needs the same treatment SpendfulnessCli got originally: read each repo's actual structure first (it's a different stack per repo — Electron desktop app, REST API, mobile, WebSockets — so don't copy KitCli's or another repo's conventions verbatim), then write a tailored `CONTRIBUTING.md` per repo.

**Why:** Surfaced while auditing what a "SoloCAIRN pipeline" (points, PR conventions, story-artifact choice) should look like for a repo that doesn't have any process documented yet at all — Diagnosea was the concrete example, deferred rather than done blind.

**How to apply:** When this becomes active work, don't assume it needs the exact same conventions as KitCli/YnabSharp/SpendfulnessCli (see [[methodology_four_homes_framework]] on not over-applying one repo's specifics elsewhere) — read each Diagnosea repo's actual code/structure first, the way SpendfulnessCli's `CONTRIBUTING.md` was written from its real ADR/CONCEPTS.md layout rather than copied from KitCli's.

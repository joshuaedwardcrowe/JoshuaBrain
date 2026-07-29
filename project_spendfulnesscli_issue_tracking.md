---
name: project-spendfulnesscli-issue-tracking
description: "How SpendfulnessCli issues are organized, estimated, and mapped to GitHub Projects boards"
metadata: 
  node_type: memory
  type: project
  originSessionId: 681f9a31-eb28-4ccf-8913-2eb0f7bd2929
  modified: 2026-07-28T18:24:35.302Z
---

SpendfulnessCli issue-tracking conventions (learned via GitHub API/GraphQL, not visible in repo files):

- **Labels**: `User Value` (direct end-user value) vs `Developer Value`/`Tech Debt` (internal/plumbing work). Not an Agile "As a user..." story format — just a value classification.
- **Decomposition**: Large `User Value` issues get broken into GitHub sub-issues (parent/child via the sub-issues API). Effort/estimates live on the leaf sub-issues, not the parent story — e.g. #163 "Splittable Transactions Personalisation" (User Value) has no Estimate itself; its sub-issues #164–168 do.
- **Estimates**: Tracked in a user-owned GitHub Projects v2 board, not labels: "YNAB Analysis & Automation" (https://github.com/users/joshuaedwardcrowe/projects/8), which has a numeric `Estimate` field, Fibonacci-ish scale (observed values: 2, 3, 8). Reading/writing this requires the `project` gh auth scope (`gh auth refresh -s project`) — default `gh` scopes don't include it.
- **Project #8 scope** (per user, 2026-07-28): represents commands that **analyse** YNAB data or do **CRUD** operations on it. Other user projects exist but are unexplored: #5 "Creating a Proof of Concept", #2 "Adding Settings", #1 "Tech Debt Monitoring" — likely narrower/different scopes.
- Also relevant: milestone "Measuring Spendfulness" groups issues about measuring/tracking spendfulness specifically (financial goals, emotional spending periods) — see [[project_spendfulnesscli_mission]].

**Why:** This structure isn't derivable from the codebase — it lives in GitHub's issue/label/project metadata. Re-deriving it via API calls each session wastes calls the user has already spent time confirming.

**How to apply:** When raising or estimating SpendfulnessCli issues: classify as `User Value` vs `Developer Value`/`Tech Debt`; if it's an analysis or CRUD command, it likely belongs on project #8; break large stories into sub-issues before assigning Estimate values, and put the Estimate on the sub-issues rather than the parent.

## Feedback — reactive corrections (a specific mistake, don't repeat it)

- [Permission prompts](feedback_permission_prompts.md) — discuss adding a permanent allow rule instead of re-prompting; check for a phrasing fix first
- [PR comment audit](feedback_pr_comment_audit.md) — check both pulls/comments (inline) and issues/comments (top-level) endpoints, not just one
- [Memory editing style](feedback_memory_editing_style.md) — rewrite corrected facts as clean current-state snapshots, no correction narrative
- [Milestone naming convention](feedback_milestone_naming_convention.md) — name after the external spec/version (e.g. `YNAB API v1.86.0`), not a goal description
- [Sub-issue chronological order](feedback_subissue_chronological_order.md) — hard rule: sub-issues must be planned jointly for delivery order; new projects start with a planning spike (mixed: rule + a sequencing mistake it came from)
- [Spike outcome rule](feedback_spike_outcome_rule.md) — spike resolves to new-complexity or no-new-complexity; latter closes the spike and opens a fresh ticket (mixed: rule + how it was learned)
- [Idea routing](feedback_idea_routing.md) — future feature ideas go on the GitHub Ideas project board as an issue, not into memory
- [Issue closure requires agreement](feedback_issue_closure_requires_agreement.md) — never word a PR/summary as "closing" an issue or use GitHub auto-close keywords until the user has agreed the PR resolves it
- [PR review response triage](feedback_pr_review_response_triage.md) — sort review comments into fix/question/out-of-scope-idea and share the triage before editing any files

## Feedback — methodology (stated working practices, not corrections)

- [PR size limit](methodology_pr_size_limit.md) — max 20 files per PR (10-15 preferred), across every repo, plan splits upfront
- [Test code conventions](methodology_test_code_conventions.md) — reusable test doubles, serialize real DTOs not raw JSON, name doubles Test* — across every repo
- [Engineering estimation pipeline](methodology_engineering_estimation_pipeline.md) — WAG (worth pursuing?) → SWAG (prioritize) → inception spike (validates estimate, sets milestones) → per-issue Estimates
- [Issue title convention](methodology_issue_title_convention.md) — plain-language pre-WAG, Conventional Commits `type(scope):` once a spike carves out delivery sub-issues
- [JoshuaBrain push policy](methodology_joshuabrain_push_policy.md) — commit and push memory changes to JoshuaBrain immediately, not periodically
- [Four homes framework](methodology_four_homes_framework.md) — CAIRN (any team) / SoloCAIRN (any solo maintainer) / JoshuaBrain (personal only) / each repo's own CONTRIBUTING.md (binding, per-repo, incl. simulated-org infra)
- [Traditional project board layout](methodology_traditional_project_board_layout.md) — delivery board Status pipeline Backlog→Done, Estimate, Priority High/Medium/Low (standardize #8's P0/P1/P2 outlier)
- [Idea board layout](methodology_idea_board_layout.md) — Ideas board Status renamed to pipeline stages: New (pre-WAG)→WAG'd→SWAG'd/Prioritized→Released
- [Docs folder layout](methodology_docs_folder_layout.md) — docs/{adr,concepts,reviews} w/ 0000-template.md applies to every repo incl. SpendfulnessCli; its flat ADR/+CONCEPTS.md is a gap, tracked as SpendfulnessCli#195

## Project context — routed by which repo/ecosystem is active

- [SpendfulnessCli mission](project_spendfulnesscli_mission.md) — CLI's guiding mission is helping users be "spendful" per SPENDFULNESS.md's four-axis framework
- [SpendfulnessCli issue tracking](project_spendfulnesscli_issue_tracking.md) — User Value/sub-issue/Estimate conventions; project #8 = analyse+CRUD commands
- [KitCli vision](project_kitcli_vision.md) — conventions/extensibility framework like ASP.NET Web API or Umbraco
- [SpendfulnessCli/KitCli split history](project_spendfulnesscli_kitcli_split_history.md) — old SpendfulnessCli issues can be misfiled framework concerns; migrate to KitCli, don't just triage locally
- [Diagnosea CONTRIBUTING.md bootstrap](project_diagnosea_contributing_bootstrap.md) — no repo has one (2 of 8 empty); tracked as 8 repo-scoped issues on Diagnosea's own Ideas board, not here

## References — pointers to external systems

- [SoloCAIRN](https://github.com/joshuaedwardcrowe/SoloCAIRN) — fork of Abdullah Siddique's CAIRN, adapted for solo/AI-assisted delivery; the ecosystem's Build-stage methodology
- [JoshuaBrain](https://github.com/joshuaedwardcrowe/JoshuaBrain) — this memory, git-backed (this repo itself)

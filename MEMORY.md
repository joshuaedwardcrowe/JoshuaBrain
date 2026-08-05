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
- [Commit message describes change](feedback_commit_message_describes_change.md) — title the diff, never the process ("address review" banned) — across every repo
- [Check PR conventions before opening](feedback_check_pr_conventions_before_opening.md) — read the repo's PR template + a couple recent PRs before `gh pr create`, don't invent title/body format
- [Use the gh stack extension](feedback_use_gh_stack_extension.md) — stacked PRs are a real GitHub feature with `gh stack` installed; never hand-chain `--base` (it adopts existing branches too)
- [Refer to issues by title](feedback_refer_to_issues_by_title.md) — lead with the issue's title in conversation, never the bare number alone

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
- [PR mirrors issue metadata](methodology_pr_mirrors_issue_metadata.md) — PRs should carry their linked issue's labels/milestone, applied per-repo (not a SoloCAIRN rule) — across every repo
- [Cross-repo propagation](methodology_cross_repo_propagation.md) — once a convention spans multiple repos, apply it to all of them in the same sitting, not just the one that triggered it
- [Post plan to issue](methodology_post_plan_to_issue.md) — after plan mode approval, post the plan as an issue comment before coding; personal convention, lives in memory not CONTRIBUTING.md
- [Docs-only direct to main](methodology_docs_only_direct_to_main.md) — docs-only changes skip the PR flow, across every repo including KitCli/YnabSharp now

## Project context — routed by which repo/ecosystem is active

- [SpendfulnessCli mission](project_spendfulnesscli_mission.md) — CLI's guiding mission is helping users be "spendful" per SPENDFULNESS.md's four-axis framework
- [SpendfulnessCli reorganisation use-case](project_spendfulnesscli_reorganisation_usecase.md) — bulk re-org of categories/groups/transactions is milestone-level; user re-shuffles their budget every couple years
- [SpendfulnessCli issue tracking](project_spendfulnesscli_issue_tracking.md) — User Value/sub-issue/Estimate conventions; project #8 = analyse+CRUD commands
- [KitCli vision](project_kitcli_vision.md) — conventions/extensibility framework like ASP.NET Web API or Umbraco
- [SpendfulnessCli/KitCli split history](project_spendfulnesscli_kitcli_split_history.md) — old SpendfulnessCli issues can be misfiled framework concerns; migrate to KitCli, don't just triage locally
- [Diagnosea CONTRIBUTING.md bootstrap](project_diagnosea_contributing_bootstrap.md) — no repo has one (2 of 8 empty); tracked as 8 repo-scoped issues on Diagnosea's own Ideas board, not here

## References — pointers to external systems

- [SoloCAIRN](https://github.com/joshuaedwardcrowe/SoloCAIRN) — fork of Abdullah Siddique's CAIRN, adapted for solo/AI-assisted delivery; the ecosystem's Build-stage methodology
- [JoshuaBrain](https://github.com/joshuaedwardcrowe/JoshuaBrain) — this memory, git-backed (this repo itself)

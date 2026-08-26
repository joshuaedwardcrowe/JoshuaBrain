# Branches, PRs and comments

Full reasoning: the named files in `~/.claude/projects/-Users-joshuacrowe/memory/`.

- **Ask before merging any PR or branch**, every time, however confident the change.
- **Docs-only changes go straight to `main`** in any personal-account or KitCli-org
  repo. Code plus docs still goes through a PR. (`methodology_docs_only_direct_to_main`)
- **Maximum 20 files per PR, 10–15 preferred.** Find the split before opening it, not
  after. (`methodology_pr_size_limit`)
- **Stack with `gh stack`** — it is installed, and it adopts existing branches:
  `gh stack init <bottom> … <top>` then `gh stack submit --auto`. Never hand-chain
  `--base`. (`feedback_use_gh_stack_extension`)
- **Read `.github/PULL_REQUEST_TEMPLATE.md` and two or three recent merged PRs before
  `gh pr create`.** Use the structure they show.
  (`feedback_check_pr_conventions_before_opening`)
- **Mirror the linked issue's labels and milestone onto the PR** — GitHub doesn't.
  (`methodology_pr_mirrors_issue_metadata`)
- **Commit and PR titles describe the diff, never the process.** "address review",
  "apply feedback" and "fix comments" are banned shapes.
  (`feedback_commit_message_describes_change`)
- **Audit both comment endpoints with `--paginate` before merging**, not only when
  asked: `repos/{owner}/{repo}/pulls/{n}/comments` for inline,
  `repos/{owner}/{repo}/issues/{n}/comments` for top-level. (`feedback_pr_comment_audit`)
- **Triage review comments into mechanical fix / question for the thread / design or
  out-of-scope idea, and share the triage before editing anything.** In-scope means code
  this PR touches, so a comment can split across buckets. Reply on every thread
  individually, prefixed `🤖 **Claude:**`. (`feedback_pr_review_response_triage`)
- **Bulk board writes are one aliased GraphQL request**, never a `gh project item-edit`
  loop; check `gh api rate_limit --jq '.resources'` before starting.
  (`feedback_batch_github_project_writes`)
- **Editing a `updateProjectV2Field` option regenerates every option id and blanks the
  board.** Snapshot first. (`reference_project_field_option_edits_wipe_values`)
- **On a permission prompt for repo-internal work**, check whether phrasing the command
  to match an existing allow rule fixes it (`git -C <path> …`, not `cd <path> && git …`)
  before proposing a new rule. Repo-internal shapes are worth a permanent rule; anything
  destructive or reaching outside the repo still gets asked each time.
  (`feedback_permission_prompts`)

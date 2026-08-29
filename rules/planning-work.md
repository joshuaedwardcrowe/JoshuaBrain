# Planning work

Full reasoning: the named files in `~/.claude/projects/-Users-joshuacrowe/memory/`.

- **Search before proposing.** `gh issue list --search "<topic> in:title" --state all`.
  An existing issue sets the deliverable, the doc type and the verdict format.
  (`feedback_search_issues_before_proposing`)
- **Read the repo's `CONTRIBUTING.md` and `.github/ISSUE_TEMPLATE/` before filing,
  labelling, routing or spiking** — not afterwards.
  (`feedback_check_pr_conventions_before_opening`)
- **Pipeline: WAG → SWAG → inception spike → per-issue estimates.** Don't skip a gate or
  propose a spike before greenlight. (`methodology_engineering_estimation_pipeline`)
- **Issue titles**: plain-language problem statement at idea stage; `type(scope):
  description` once a spike carves out delivery sub-issues. Don't retitle old ones.
  (`methodology_issue_title_convention`)
- **Every ticket body is laymen's terms** — problem first in plain words, so someone
  with no domain knowledge can pick it up; name a type only where the implementer must
  type it. Dense sibling tickets are not a licence to match them.
  (`feedback_tickets_in_laymens_terms`)
- **Never decompose into sub-issues alone.** Delivery order is agreed with the user
  first, a handful at a time; a new project opens with a planning spike.
  (`feedback_subissue_chronological_order`)
- **A spike's verdict asks whether the work is as small as the issue assumed**, not
  whether its questions got answered. No new complexity: close the spike, open a fresh
  delivery ticket. New complexity: parent stays open, work hangs off it.
  (`feedback_spike_outcome_rule`)
- **Never move a Status field past a human-verification value** — In QA, Done, and the
  like. Attach the evidence and let the human move the card.
  (`feedback_no_self_moving_status_gates`)
- **Never word a PR or a summary as "closing" an issue**, and never use closing
  keywords, until the user has agreed the work resolves it.
  (`feedback_issue_closure_requires_agreement`)
- **Name the decision a process artifact feeds, and who makes it, before adding it** —
  velocity, iterations, reports, board fields. Won't complete the sentence, don't add
  it. (`feedback_no_process_without_a_consumer`)
- **Post the agreed plan as an issue comment before the first commit**, prefixed
  `🤖 **Claude:**`. (`methodology_post_plan_to_issue`)
- **Name a milestone after the external spec version it tracks**, not a goal.
  (`feedback_milestone_naming_convention`)
- **A convention confirmed to span repos is applied to every repo it governs in the
  same sitting.** (`methodology_cross_repo_propagation`)

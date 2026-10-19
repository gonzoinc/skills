---
name: setup-collection
description: "Inspect and configure project conventions for the selected Gonzo Skills workflows, reusing existing guidance."
---

## Collection policy

Activate this skill only after the user explicitly requests it or accepts a recommendation. Recommendations are allowed; wait for acceptance before activating **any supporting skill**, including from a handoff, note or another skill. Reading a candidate for comparison does not authorize executing it. Skill references below are recommendations, never automatic calls. The user-authorized exception is `post-mortem`: it may automatically record unexpected failures and consult recovery history without activating another workflow.

Follow applicable user and project rules, existing documentation and artifact locations, and the canonical project workspace. Do not create parallel guidance or silently replace existing skills. Use the project's established context sources and normal filesystem tools. Delegate only when authorized and useful.

Put all agent working files in the active project or working folder's primary `.codex/` directory. Remove your temporary scripts, dependencies, captures, logs and intermediates when no longer needed, before reporting completion. Only intended deliverables and maintained project source belong elsewhere. Preserve user-owned and unrelated files; explain any working material retained for unfinished work or reproducibility.

Use short slash names in user-facing recommendations and usage examples, such as `/diagnose-bugs` or `/grilling`; do not require users to type a `gonzo-skills:` prefix. In the desktop app these select skills through the slash menu. Mention the collection name only when needed to distinguish duplicate entries. User acceptance still gates each supporting workflow.

When gathering user input, ask one concise question, optionally give a recommendation, and wait for the answer before asking the next. Do not hide several independent questions inside one sentence or form. Reuse settled answers. This governs the live interview; a requested questionnaire or specification may contain multiple questions or requirements as its deliverable.

Keep secrets out of commands shown to the user and saved artifacts. Use research and browser tools permitted by the active project and user. External publishing and production changes require the applicable user authorization and a concrete reviewable result first. Do not infer that acceptance of this workflow authorizes unrelated writes.

For any user-assisted action, first explain the single action needed, ask whether the user is ready, and stop. Only after explicit readiness request the action and begin dependent capture, monitoring or interactive work. Then stop and wait for completion or the actual result; silence and elapsed time are not completion. Allow adequate time without an arbitrary short timeout.

# Setup Collection

Configure only the selected workflows, on explicit request. This skill does not install or enable plugins, modify global skills, set up issue triage, create labels, or add integrations.

1. Inspect the active workspace, remotes, applicable guidance, existing plans, domain language, decision records, tracker conventions, and available skills. Check for an earlier collection setup and preserve user edits. Do not assume GitHub Issues merely because a remote exists.
2. Summarize what already supplies the needed context and what is missing. Reuse those conventions. Ask one concise question at a time only for unresolved choices: where work is tracked, where domain terms and decisions live, or which selected workflows need configuration. Give a recommendation and wait for each answer.
3. Show the exact proposed edits and paths before applying substantive changes to guidance. Configure only selected skills. A pointer should name a workflow as an optional recommendation requiring user acceptance, never an automatic trigger. Do not change another skill's invocation policy.
4. After the user accepts the proposed edits, update the existing files in place. Create new notes only where authorized by project conventions or a separate location decision. Preserve explicit user rules and surrounding content. No external writes follow from setup alone.
5. Report the files changed and any unresolved setup. If existing context was sufficient, report that no edits were needed.

Use these seed references only for the chosen context, adapting their example paths to the project:

- [domain.md](domain.md): domain-document consumer conventions.
- [issue-tracker-local.md](issue-tracker-local.md): local specs and dependency-linked tickets.
- [issue-tracker-github.md](issue-tracker-github.md): GitHub operations when GitHub tracking was chosen.
- [issue-tracker-gitlab.md](issue-tracker-gitlab.md): GitLab operations when GitLab tracking was chosen.

No tracker setup is required merely to diagnose, review, teach, interview, draft, or research.

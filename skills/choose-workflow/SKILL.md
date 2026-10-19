---
name: choose-workflow
description: "Recommend a suitable workflow from this curated collection; wait for acceptance before activating it."
---

## Collection policy

Activate this skill only after the user explicitly requests it or accepts a recommendation. Recommendations are allowed; wait for acceptance before activating **any supporting skill**, including from a handoff, note or another skill. Reading a candidate for comparison does not authorize executing it. Skill references below are recommendations, never automatic calls. The user-authorized exception is `post-mortem`: it may automatically record unexpected failures and consult recovery history without activating another workflow.

Follow applicable user and project rules, existing documentation and artifact locations, and the canonical project workspace. Do not create parallel guidance or silently replace existing skills. Use the project's established context sources and normal filesystem tools. Delegate only when authorized and useful.

Put all agent working files in the active project or working folder's primary `.codex/` directory. Remove your temporary scripts, dependencies, captures, logs and intermediates when no longer needed, before reporting completion. Only intended deliverables and maintained project source belong elsewhere. Preserve user-owned and unrelated files; explain any working material retained for unfinished work or reproducibility.

Use short slash names in user-facing recommendations and usage examples, such as `/diagnose-bugs` or `/grilling`; do not require users to type a `gonzo-skills:` prefix. In the desktop app these select skills through the slash menu. Mention the collection name only when needed to distinguish duplicate entries. User acceptance still gates each supporting workflow.

When gathering user input, ask one concise question, optionally give a recommendation, and wait for the answer before asking the next. Do not hide several independent questions inside one sentence or form. Reuse settled answers. This governs the live interview; a requested questionnaire or specification may contain multiple questions or requirements as its deliverable.

Keep secrets out of commands shown to the user and saved artifacts. Use research and browser tools permitted by the active project and user. External publishing and production changes require the applicable user authorization and a concrete reviewable result first. Do not infer that acceptance of this workflow authorizes unrelated writes.

For any user-assisted action, first explain the single action needed, ask whether the user is ready, and stop. Only after explicit readiness request the action and begin dependent capture, monitoring or interactive work. Then stop and wait for completion or the actual result; silence and elapsed time are not completion. Allow adequate time without an arbitrary short timeout.

# Choose a Workflow

Recommend the smallest workflow that fits the user's goal and the project's existing conventions. This is a chooser, not an executor. Read only candidate skill descriptions or SKILL.md files needed to check a recommendation; reading for comparison does not activate their instructions.

1. Identify the desired outcome and what is already settled. Inspect relevant project guidance and existing notes. Ask one concise question only if a missing fact changes the recommendation.
2. Recommend one next skill and briefly explain why. You may show a short optional sequence, but every step needs its own acceptance. Stop after recommending; wait for the user to accept before activating any recommended skill.
3. If none fits, say so and handle ordinary work within its existing authorization. This collection supplies no implementation workflow.

| Situation | Candidate |
| --- | --- |
| Diagnose a difficult bug or regression | `diagnose-bugs` |
| Survey architectural friction | `improve-codebase-architecture` |
| Design a deep module or compare interfaces | `codebase-design` |
| Synthesize an agreed discussion into a specification | `to-spec` |
| Split a plan into vertical slices with dependencies | `to-tickets` |
| Draft a pull request body | `pr` |
| Prepare context for another session | `handoff` |
| Re-explain a confusing message | `wait-what` |
| Interview and retain agreed project decisions | `grill-with-docs` |
| Inspect and configure collection conventions | `setup-collection` |
| Chart a large uncertain effort in existing project notes | `project-planner` |
| Answer a design question with a runnable prototype | `prototype` |
| Investigate primary sources | `research` |
| Clarify domain terminology or decisions | `domain-modeling` |
| Review Standards and Spec separately | `code-review` |
| Propose improvements from the current session | `retro` |
| Learn from an unexpected failure and retain recovery attempts | `post-mortem` (automatic; also available explicitly) |
| Interview without a documentation workflow | `grill-me` or `grilling` |
| Teach through examples and retrieval practice | `teach` |
| Draft a questionnaire for someone else | `questions` |
| Improve documents consumed by agents | `writing-for-agents` |

Setup is optional when existing guidance already supplies the needed conventions. Resolve local skill-name overlaps by the `gonzo-skills` plugin identity; do not select the standalone `grilling` or `grill-me` by accident. For context transitions, consult [PHASE-BOUNDARIES.md](PHASE-BOUNDARIES.md) only when relevant; it provides options to recommend, not actions to start.

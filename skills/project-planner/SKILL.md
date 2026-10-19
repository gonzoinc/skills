---
name: project-planner
description: "Plan a large uncertain effort as a decision map in existing project notes, resolving decisions before implementation."
---

## Collection policy

Activate this skill only after the user explicitly requests it or accepts a recommendation. Recommendations are allowed; wait for acceptance before activating **any supporting skill**, including from a handoff, note or another skill. Reading a candidate for comparison does not authorize executing it. Skill references below are recommendations, never automatic calls. The user-authorized exception is `post-mortem`: it may automatically record unexpected failures and consult recovery history without activating another workflow.

Follow applicable user and project rules, existing documentation and artifact locations, and the canonical project workspace. Do not create parallel guidance or silently replace existing skills. Use the project's established context sources and normal filesystem tools. Delegate only when authorized and useful.

Put all agent working files in the active project or working folder's primary `.codex/` directory. Remove your temporary scripts, dependencies, captures, logs and intermediates when no longer needed, before reporting completion. Only intended deliverables and maintained project source belong elsewhere. Preserve user-owned and unrelated files; explain any working material retained for unfinished work or reproducibility.

Use short slash names in user-facing recommendations and usage examples, such as `/diagnose-bugs` or `/grilling`; do not require users to type a `gonzo-skills:` prefix. In the desktop app these select skills through the slash menu. Mention the collection name only when needed to distinguish duplicate entries. User acceptance still gates each supporting workflow.

When gathering user input, ask one concise question, optionally give a recommendation, and wait for the answer before asking the next. Do not hide several independent questions inside one sentence or form. Reuse settled answers. This governs the live interview; a requested questionnaire or specification may contain multiple questions or requirements as its deliverable.

Keep secrets out of commands shown to the user and saved artifacts. Use research and browser tools permitted by the active project and user. External publishing and production changes require the applicable user authorization and a concrete reviewable result first. Do not infer that acceptance of this workflow authorizes unrelated writes.

For any user-assisted action, first explain the single action needed, ask whether the user is ready, and stop. Only after explicit readiness request the action and begin dependent capture, monitoring or interactive work. Then stop and wait for completion or the actual result; silence and elapsed time are not completion. Allow adequate time without an arbitrary short timeout.

# Project Planner

For work too uncertain to hold in one session, maintain a shared **decision map**. Produce decisions, not implementation deliverables. If the work is already well scoped, recommend a smaller workflow and wait for acceptance.

## The map

Find and reuse the project's existing plan or notes. Keep the map there as the canonical record; do not create a competing tracker or documentation tree. Use human-readable decision names and links, rather than bare identifiers.

The map contains:

- **Destination**: what a clear route would let the user decide or specify.
- **Notes**: constraints, accepted conventions, and optional workflow recommendations.
- **Decisions so far**: a short index pointing to the agreed answers.
- **Open decisions**: specific questions with type, status, dependencies, and links to detail.
- **Not yet specified**: in-scope uncertainties that cannot yet be phrased as precise questions.
- **Out of scope**: exclusions and their reasons, separate from completed decisions.

Each open decision records its question, blockers, status (open, claimed, resolved, out of scope), and answer when resolved. Use existing note headings, identifiers and formats. A single notes file with anchors is sufficient; create separate records only when the project already does so. The **frontier** is open, unclaimed decisions whose blockers are resolved.

## Chart the route

1. Read the current plan, relevant code, terminology and prior decisions. Name the destination with the user, asking one concise question at a time and recommending an answer. Wait for each reply.
2. Explore breadth first to identify the decisions that gate progress. Separate precisely stated questions from the fog that depends on unanswered choices. Record only what is known, with explicit uncertainties.
3. Draft or update the map in the existing notes and connect blockers using real local links. Preserve other sessions' edits and claims.
4. Recommend the next frontier decision. Do not launch supporting workflows, agents or new chats automatically.

## Resolve a decision

Load the map and relevant linked detail. Work the user-selected decision, or the first frontier decision if none was specified. Mark its claim in the existing notes to avoid duplicate work. Default to resolving one substantive decision per session; research may settle several factual prerequisites.

- **Research**: investigate primary sources directly. Recommend `research` if useful; activate only after acceptance. Delegation requires separate authorization and a useful scope.
- **Prototype**: identify the concrete question and recommend `prototype`. Wait for acceptance before building it.
- **Interview**: ask one concise question with a recommendation, wait, and use existing answers. Recommend `grilling` or `domain-modeling` only if their separate workflows would help.
- **Prerequisite task**: identify what must happen before a decision can be made. Perform only authorized work. For user-assisted steps, explain the single action, ask readiness and wait; after confirmation request the action, then wait for completion before dependent work.

Record confirmed resolutions, update the decision index, and promote newly precise fog into open decisions. Keep tentative terms or choices marked as proposals until confirmed. Mark mis-scoped decisions out of scope with a reason. Do not delete unresolved history.

External tickets, comments, assignments, closure, labels, branch publication and pull requests occur **only when requested**. If requested, first prepare concrete drafts and dependency relationships for review; use the established tracker and existing authorization. No research or prototype branches are pushed automatically.

When the route is clear, summarize the decisions and remaining execution work. Recommend `to-spec` or `to-tickets` when useful and wait for acceptance; do not implement from the map automatically.

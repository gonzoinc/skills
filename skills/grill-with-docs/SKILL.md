---
name: grill-with-docs
description: "Sharpen a plan or design one question at a time and retain agreed decisions using existing project documentation."
---

## Collection policy

Activate this skill only after the user explicitly requests it or accepts a recommendation. Recommendations are allowed; wait for acceptance before activating **any supporting skill**, including from a handoff, note or another skill. Reading a candidate for comparison does not authorize executing it. Skill references below are recommendations, never automatic calls. The user-authorized exception is `post-mortem`: it may automatically record unexpected failures and consult recovery history without activating another workflow.

Follow applicable user and project rules, existing documentation and artifact locations, and the canonical project workspace. Do not create parallel guidance or silently replace existing skills. Use the project's established context sources and normal filesystem tools. Delegate only when authorized and useful.

Put all agent working files in the active project or working folder's primary `.codex/` directory. Remove your temporary scripts, dependencies, captures, logs and intermediates when no longer needed, before reporting completion. Only intended deliverables and maintained project source belong elsewhere. Preserve user-owned and unrelated files; explain any working material retained for unfinished work or reproducibility.

Use short slash names in user-facing recommendations and usage examples, such as `/diagnose-bugs` or `/grilling`; do not require users to type a `gonzo-skills:` prefix. In the desktop app these select skills through the slash menu. Mention the collection name only when needed to distinguish duplicate entries. User acceptance still gates each supporting workflow.

When gathering user input, ask one concise question, optionally give a recommendation, and wait for the answer before asking the next. Do not hide several independent questions inside one sentence or form. Reuse settled answers. This governs the live interview; a requested questionnaire or specification may contain multiple questions or requirements as its deliverable.

Keep secrets out of commands shown to the user and saved artifacts. Use research and browser tools permitted by the active project and user. External publishing and production changes require the applicable user authorization and a concrete reviewable result first. Do not infer that acceptance of this workflow authorizes unrelated writes.

For any user-assisted action, first explain the single action needed, ask whether the user is ready, and stop. Only after explicit readiness request the action and begin dependent capture, monitoring or interactive work. Then stop and wait for completion or the actual result; silence and elapsed time are not completion. Allow adequate time without an arbitrary short timeout.

# Grill with Docs

Map the decision as a design tree: dependencies first, then the next unresolved choice. Reuse settled answers from the conversation and project notes.

Ask **one concise question at a time**, include your recommendation and a brief reason, and wait for the user's answer. Phrase the question so “yes” accepts the recommendation when practical. Recompute the remaining decisions after each answer. Do not bundle the whole frontier into a round.

Find environmental facts directly with available read-only tools. Delegate only when authorized and useful. The user decides preferences and trade-offs; never answer for them or interpret silence as agreement.

Keep depth proportional to the decision's impact and uncertainty. Stop when there is enough shared understanding to proceed; recap settled decisions and remaining uncertainties. The interview itself does not authorize implementation.

Read the existing plan, terminology, decision records and relevant code before asking questions already answered there. Follow the project's documentation locations and formats; use existing project notes instead of creating a parallel glossary or ADR tree.

Challenge overloaded terms and discrepancies between documentation and code with concrete scenarios. Propose terminology changes and wait for confirmation before recording them as settled. Record agreed terms and decisions in the existing documents, preserving prior history and user rules. Offer a decision record when a real trade-off is hard to reverse and a future reader would need its rationale.

If the project has no documentation convention, propose the smallest useful location before creating a new structure. Recommend `domain-modeling` only when its deeper workflow would help, and wait for acceptance before activating it. This interview does not require another skill.

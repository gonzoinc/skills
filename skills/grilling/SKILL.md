---
name: grilling
description: "Stress-test a plan, decision, or idea through one concise question at a time."
---

## Collection policy

Activate this skill only after the user explicitly requests it or accepts a recommendation. Recommendations are allowed; wait for acceptance before activating **any supporting skill**, including from a handoff, note or another skill. Reading a candidate for comparison does not authorize executing it. Skill references below are recommendations, never automatic calls. The user-authorized exception is `post-mortem`: it may automatically record unexpected failures and consult recovery history without activating another workflow.

Follow applicable user and project rules, existing documentation and artifact locations, and the canonical project workspace. Do not create parallel guidance or silently replace existing skills. Use the project's established context sources and normal filesystem tools. Delegate only when authorized and useful.

Put all agent working files in the active project or working folder's primary `.codex/` directory. Remove your temporary scripts, dependencies, captures, logs and intermediates when no longer needed, before reporting completion. Only intended deliverables and maintained project source belong elsewhere. Preserve user-owned and unrelated files; explain any working material retained for unfinished work or reproducibility.

Use short slash names in user-facing recommendations and usage examples, such as `/diagnose-bugs` or `/grilling`; do not require users to type a `gonzo-skills:` prefix. In the desktop app these select skills through the slash menu. Mention the collection name only when needed to distinguish duplicate entries. User acceptance still gates each supporting workflow.

When gathering user input, ask one concise question, optionally give a recommendation, and wait for the answer before asking the next. Do not hide several independent questions inside one sentence or form. Reuse settled answers. This governs the live interview; a requested questionnaire or specification may contain multiple questions or requirements as its deliverable.

Keep secrets out of commands shown to the user and saved artifacts. Use research and browser tools permitted by the active project and user. External publishing and production changes require the applicable user authorization and a concrete reviewable result first. Do not infer that acceptance of this workflow authorizes unrelated writes.

For any user-assisted action, first explain the single action needed, ask whether the user is ready, and stop. Only after explicit readiness request the action and begin dependent capture, monitoring or interactive work. Then stop and wait for completion or the actual result; silence and elapsed time are not completion. Allow adequate time without an arbitrary short timeout.

# Grilling

Map the decision as a design tree: dependencies first, then the next unresolved choice. Reuse settled answers from the conversation and project notes.

Ask **one concise question at a time**, include your recommendation and a brief reason, and wait for the user's answer. Phrase the question so “yes” accepts the recommendation when practical. Recompute the remaining decisions after each answer. Do not bundle the whole frontier into a round.

## Visible question counts and branches

Before the first question, form a provisional plan of the questions currently needed. Show progress on every question turn using **Question N of T (current plan) — R remaining after this question**. `N` is the next question's sequential number, `T` is answered questions plus currently planned unanswered questions, and `R = T - N`. Start at question 1. State initially that the count may change with the answers; do not present it as a fixed promise.

Count actual questions, not topics or hidden subquestions. Keep mutually exclusive or still-unknown branches out of the current count until the answer makes them relevant. Do not invent questions to reach a target count. Track progress in the conversation; no separate tracking file is needed.

After every answer, update the plan before asking the next question. When an answer opens, closes, replaces or redirects a branch, make that change visible in a short **Plan changed** line: name the branch and why it changed, state how many questions were added or removed, and show **previous total → revised total**, plus how many unanswered questions remain **including the next question**. Disclose a branch change even if replacements leave the total unchanged. Ordinary progress through an unchanged plan needs only the progress line.

For example: **Plan changed:** external customers introduce an access-control branch; 2 questions added, **6 → 8 total**, **5 unanswered including the next question**. Then show **Question 4 of 8 (current plan) — 4 remaining after this question**, ask only that question with your recommendation, and wait.

Keep answered question numbers stable when the plan changes. If an answer also settles other planned questions, remove those from the plan, explain the reduction, and do not ask them again. At completion, show the number of questions answered and **0 remaining**, then recap the decisions. If unresolved questions are deferred, show their count explicitly instead of claiming completion.

Find environmental facts directly with available read-only tools. Delegate only when authorized and useful. The user decides preferences and trade-offs; never answer for them or interpret silence as agreement.

Keep depth proportional to the decision's impact and uncertainty. Stop when there is enough shared understanding to proceed; recap settled decisions and remaining uncertainties. The interview itself does not authorize implementation.

# Gonzo Skills

23 Codex skills for planning, debugging, design, review and learning from mistakes.
Includes 22 workflows adapted from [Matt Pocock's skills](https://github.com/mattpocock/skills), with
explicit activation for those workflows, one question at a time and respect for existing project conventions.
The original `post-mortem` skill runs automatically after unexpected failures.

## Installation

### 1. Install the collection

In a terminal with the Codex CLI available, run:

```sh
codex plugin marketplace add gonzoinc/skills
codex plugin add gonzo-skills@gonzo-skills
```

`gonzo-skills` is the marketplace name defined by this repository, including when
you install it from GitHub. See the [official marketplace documentation](https://developers.openai.com/plugins/build/plugins)
for supported source types.

Already have a local checkout? Register its folder instead of the GitHub source:

```sh
codex plugin marketplace add "<repository-path>"
codex plugin add gonzo-skills@gonzo-skills
```

Use one installation source for this collection. Installing individual copies as
well can leave duplicate skills in the command list.

### 2. Select a skill

In the Codex desktop composer, type `/` followed by a skill name and select its
entry. For example, type `/diagnose-bugs` or `/grilling`.
You do not need to type `gonzo-skills:`. If names overlap with another collection,
choose the Gonzo Skills entry.

These are selections from the [slash command list](https://learn.chatgpt.com/docs/reference/slash-commands),
rather than separately registered command aliases.

### 3. Start with the workflow you need

Try [`/choose-workflow`](skills/choose-workflow/SKILL.md) if you want a recommendation.
It suggests a next step and waits for you to accept it.

[`/setup-collection`](skills/setup-collection/SKILL.md) is optional. It can help
establish where project documents belong and which existing tracker conventions
to use. It proposes guidance changes before writing them.

## How this collection works

The 22 adapted workflows require an explicit request or acceptance of a
recommendation and set `policy.allow_implicit_invocation: false`. Selecting one
does not authorize a chain of other manual workflows.

**`post-mortem` is the automatic exception.** It logs unexpected failures and every
recovery attempt in the project memory bank, falling back to
`.codex/memory-bank/post-mortem.md`. Before retrying, it checks past attempts; a
repeat needs recorded new evidence or changed conditions. It stays quiet during
routine recovery and distinguishes unresolved issues from verified fixes.
Its `allow_implicit_invocation: true` enables automatic model selection; it is
not a background service or an enforced hook after every failed command.
It is also available [as a standalone skill](https://github.com/gonzoinc/post-mortem).
Install it through one package to avoid duplicate copies.

Live interviews ask **one question at a time** and wait for your answer.
[`/grilling`](skills/grilling/SKILL.md) and [`/grill-me`](skills/grill-me/SKILL.md)
also display the current question, planned total and remaining count. If an
answer opens, closes or redirects a branch, they explain the change and update
the count. A requested questionnaire can still contain multiple questions in
the finished document.

The workflows reuse existing project terminology, document locations and
context-loading conventions. Agent working files belong in the
project's `.codex/` folder and must be cleaned up. These rules guide the agent;
they do not provide filesystem enforcement.

Existing standalone skills retain their own activation policies. This collection
does not change those copies.

## Skills

Each command below links directly to its skill instructions.

### Planning and decisions

| Skill | What it does |
| --- | --- |
| [`/choose-workflow`](skills/choose-workflow/SKILL.md) | Recommends the smallest useful workflow for your situation, then waits for acceptance. |
| [`/grill-me`](skills/grill-me/SKILL.md) | Stress-tests a plan or idea through a focused interview, with visible question counts and branch updates. |
| [`/grilling`](skills/grilling/SKILL.md) | Probes assumptions and unresolved decisions one question at a time, with a recommendation and an updated question plan. |
| [`/grill-with-docs`](skills/grill-with-docs/SKILL.md) | Interviews you while maintaining confirmed terminology and decisions in existing project documentation. |
| [`/project-planner`](skills/project-planner/SKILL.md) | Maps a large effort into decisions, blockers and next steps that can span multiple sessions. |
| [`/to-spec`](skills/to-spec/SKILL.md) | Turns an existing discussion into a concrete specification with clear scope and module boundaries. |
| [`/to-tickets`](skills/to-tickets/SKILL.md) | Breaks a plan or specification into deliverable tickets with explicit dependencies. |
| [`/questions`](skills/questions/SKILL.md) | Drafts a questionnaire for someone whose answers are needed to resolve a decision. |

### Engineering and investigation

| Skill | What it does |
| --- | --- |
| [`/diagnose-bugs`](skills/diagnose-bugs/SKILL.md) | Reproduces and narrows a bug, tests hypotheses, and verifies the fix with a regression check. |
| [`/improve-codebase-architecture`](skills/improve-codebase-architecture/SKILL.md) | Surveys architecture improvement opportunities and presents a visual report for you to choose from. |
| [`/codebase-design`](skills/codebase-design/SKILL.md) | Designs modules with small interfaces, useful boundaries and testable behavior. |
| [`/prototype`](skills/prototype/SKILL.md) | Builds a focused prototype to explore logic, state or distinct UI approaches before production implementation. |
| [`/research`](skills/research/SKILL.md) | Investigates a question using primary sources and reports findings with citations. |
| [`/domain-modeling`](skills/domain-modeling/SKILL.md) | Clarifies project concepts, challenges ambiguous terms and records confirmed language and decisions. |
| [`/code-review`](skills/code-review/SKILL.md) | Reviews changes against both coding standards and the intended specification. |
| [`/pr`](skills/pr/SKILL.md) | Prepares a pull request description covering the change, evidence and merge risk. |

### Learning and continuity

| Skill | What it does |
| --- | --- |
| [`/setup-collection`](skills/setup-collection/SKILL.md) | Adapts the selected workflows to existing project documentation and tracker conventions. |
| [`/handoff`](skills/handoff/SKILL.md) | Condenses the current work into continuation notes for another session or agent. |
| [`/wait-what`](skills/wait-what/SKILL.md) | Re-explains a confusing message in plain language with the missing context. |
| [`/teach`](skills/teach/SKILL.md) | Teaches a concept through project examples, practice and one question at a time. |
| [`/post-mortem`](skills/post-mortem/SKILL.md) | Automatically records unexpected failures, every recovery attempt and verified fixes, consulting history before retries. |
| [`/retro`](skills/retro/SKILL.md) | Reviews the current session and proposes improvements to instructions, checks and tooling. |
| [`/writing-for-agents`](skills/writing-for-agents/SKILL.md) | Improves instructions and reference documents so agents can navigate and follow them more reliably. |

## What changed from upstream

This collection adapts 22 upstream workflows for Codex and our project rules,
and adds the original automatic `post-mortem` skill. The main changes are explicit activation throughout, shorter slash names,
single-question intake, visible interview progress, optional delegation and
reuse of existing project documents. Supporting workflows require acceptance,
and drafting an artifact does not itself authorize external publication.

Names such as `ask-matt`, `wayfinder` and `to-questionnaire` become
`choose-workflow`, `project-planner` and `questions`. The full per-skill changes
are in [MANIFEST.md](MANIFEST.md).

The upstream revision is pinned. Changes from Matt's repository are reviewed
deliberately rather than automatically merged into this collection; see
[UPSTREAM.md](UPSTREAM.md). Automatic activation and recovery decisions have been sampled; live history-writing
behavior and cross-session persistence still require end-to-end verification.

## Credits and license

Based on [mattpocock/skills](https://github.com/mattpocock/skills), with independent
adaptations maintained here. Original attribution and supporting credits are
preserved in [NOTICE.md](NOTICE.md) and the skill resources.

Released under the [MIT license](LICENSE). The `pr` skill also includes
HumanLayer material under its [MIT notice](skills/pr/LICENSE.humanlayer);
see the [source credits](skills/pr/CREDITS.md).

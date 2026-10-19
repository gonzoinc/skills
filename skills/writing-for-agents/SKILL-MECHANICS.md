# Skill mechanics

The skill-specific branch of [`writing-for-agents`](SKILL.md): what changes when the document is a skill (frontmatter, the invocation choice, and router skills). Everything else about writing it is the universal reference in `SKILL.md`.

## Invocation

The 22 adapted workflows in this collection are explicit-only. The original
`post-mortem` skill is the user-authorized automatic exception and sets
`allow_implicit_invocation: true`. Preserve this distinction. Keep a useful name and description, and set the supported Codex control in each skill's `agents/openai.yaml`:

```yaml
policy:
  allow_implicit_invocation: false
```

For manual workflows, the agent may recommend a workflow but waits for user acceptance before activating it, including supporting workflows. The automatic `post-mortem` exception records incidents and consults history without starting other workflows. Reading another skill for comparison does not authorize executing it. Do not add other automatic cross-skill calls or use Claude-specific frontmatter as a substitute for the Codex policy.

## Splitting by purpose

Split a workflow when a distinct purpose or conditional reference warrants it, preserving the intended invocation policy; new automatic exceptions require user authorization. Plain supporting references may remain beside their owning skill; do not hide another skill's workflow in a reference to bypass acceptance.

## Router skills

A chooser summarizes relevant workflows, recommends the smallest next step, and waits for acceptance. It never activates a sequence automatically. Reuse `choose-workflow` only after the user accepts that separate workflow.

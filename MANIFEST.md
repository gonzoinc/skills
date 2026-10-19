# Included skills

The 22 adapted skills are independently maintained from upstream revision
`5beb35b040e3de97e54fa9e386d7e42d15c295c2`. Each has
`agents/openai.yaml` with `policy.allow_implicit_invocation: false`.

Every entry preserves user/project authorization, user-assisted readiness and
completion gates, secret handling, external-browser use, canonical project storage,
existing artifact conventions and support-skill acceptance. Automatic skill
calls are replaced with recommendations requiring acceptance. Mandatory
delegation is conditional on authorization and usefulness. Claude-only
frontmatter controls are removed in favor of Codex policy. These common changes
apply to both the kept and customized workflows.

The shared policy follows each project's context-loading conventions, keeps
working files under the project's primary `.codex/`, requires agent-owned
cleanup, and uses short slash names in user-facing recommendations. The collection
name is used only to distinguish duplicate menu entries, not as a required prefix.
These are instructions, not a claim of filesystem enforcement.

Live intake across the collection asks one concise question and waits for an
answer, without bundling independent details into one sentence. This does not
limit the number of questions in a requested questionnaire artifact. The
`questions` workflow's recipient intake was split accordingly after an initial
native CLI test reproduced the compound-question problem.

| Upstream name | Local name | Adaptation beyond the common policy |
| --- | --- | --- |
| diagnosing-bugs | diagnose-bugs | Renamed for `/diagnose-bugs`. Keeps the feedback-loop, reproduce/minimize, ranked hypotheses, instrument, fix/regression and cleanup phases. Human loop/template now waits for readiness and actual completion; direct chat fallback when an interactive Bash terminal is unavailable. |
| improve-codebase-architecture | improve-codebase-architecture | Keeps hotspot survey, visual HTML candidates and user-selected exploration. Survey is self-contained, optional support workflows wait for acceptance, and report location follows project rules. |
| to-spec | to-spec | Keeps synthesis without a fresh interview, seam check and complete spec template. Reuses configured tracker/status conventions, requires no triage setup, and prepares a draft before authorized external publication. |
| to-tickets | to-tickets | Keeps vertical tracer bullets, wide-refactor expand/contract exception, blocking edges, approval iteration and one file/issue per ticket. Reuses established ticket paths and status conventions without label setup. |
| codebase-design | codebase-design | Keeps deep-module vocabulary, principles, dependency categories and interface comparison. Alternatives can be designed directly; parallel agents require authorization and usefulness. |
| pr | pr | Keeps the visual Summary, before/after Evidence and Merge Danger template. Original Dex Horthy/Humanlayer credits retained. Drafting does not itself publish. |
| handoff | handoff | Keeps compact continuation context, redaction and links to existing artifacts. Suggested skills require acceptance by the next agent; artifact path follows project rules before OS temp. |
| wait-what | wait-what | Keeps re-pitching with context, Simplified Technical English and project vocabulary. |
| ask-matt | choose-workflow | Replaces the upstream full-plugin router with a neutral chooser for the adapted workflows and original post-mortem skill. Recommends manual next steps, waits for acceptance, and handles existing name overlaps explicitly. |
| grill-with-docs | grill-with-docs | Self-contained one-question interview with recommendations. Reuses existing project documentation and records confirmed terms/decisions; no automatic interviewing/modeling skill calls. |
| setup-matt-pocock-skills | setup-collection | Reuses existing project conventions, configures selected skills only and proposes guidance edits before writing. No triage setup, label creation, integrations or installation. |
| wayfinder | project-planner | Keeps destination, decision map, blockers/frontier, fog, scope and resolution discipline. Canonical map lives in existing project notes. External tickets and branch publication only when requested; no automatic research agents. |
| prototype | prototype | Keeps logic/state and UI variants as separate branches. Uses authentic assets, labels prototypes, preserves them by project conventions, and separates production implementation from design exploration. No automatic archival branches, promotion or publication. |
| research | research | Primary-source investigation runs directly by default; delegation only when authorized and useful. Findings stay in conversation unless saving is requested or required by project conventions. |
| domain-modeling | domain-modeling | Keeps term challenges, scenarios, code checks, glossary discipline and sparse ADRs. Existing documentation conventions take precedence; terminology changes require confirmation before becoming settled records. |
| code-review | code-review | Retains separate Standards and Spec tracks, fixed comparison, smell heuristics and independent reporting. Direct review by default; parallel agents optional. Explicitly captures uncommitted scope for work-in-progress reviews. |
| retro | retro | Defaults to current-session evidence. Other session logs only when requested. Proposes evidence-backed guidance/tooling improvements before applying changes; optional writing workflow waits for acceptance. |
| grill-me | grill-me | Self-contained concise interview, one question/recommendation and answer at a time; no automatic `grilling` call or saved documentation. Shows current/total/remaining question counts and explains branch changes with revised totals, including unchanged totals after a branch replacement. |
| grilling | grilling | One concise question with a recommendation, wait for answer, reuse settled decisions and keep depth proportional. Shows current/total/remaining question counts and explains additions, removals or redirections with revised totals. Facts researched directly; no mandatory subagent or full-frontier rounds. |
| teach | teach | Preserves mission, proximal development, retrieval, spacing, interactive feedback and source-grounded teaching. One question at a time, project examples, conversational lessons by default; learning records and saved material only on request. |
| to-questionnaire | questions | Keeps recipient/gap intake and questionnaire drafting, template and purpose. Renames output prefix to `questions-`; uses the established deliverable location. Does not send the questionnaire. |
| writing-for-agents | writing-for-agents | Keeps pointers, information hierarchy, completion criteria and pruning concepts. Preserves explicit user rules and proposes substantive guidance edits before applying them. Skill-mechanics reference now describes Codex explicit-only policy and recommendation-only routers. |

## Original skill

`post-mortem` is an original gonzoinc skill, not a Matt Pocock import. The
collection now contains 23 skills: the 22 explicit-only workflows above and
this automatic exception (`allow_implicit_invocation: true`). It records each
unexpected failure and all recovery attempts, consults the project history
before retries, requires new evidence for repeated approaches, and preserves
verified resolutions and unresolved work. Its default history is
`.codex/memory-bank/post-mortem.md` when no project memory bank is established.
The standalone distribution is https://github.com/gonzoinc/post-mortem and
contains the same skill files. Original upstream hashes remain unchanged.

## Supporting resources

- `choose-workflow/PHASE-BOUNDARIES.md`: context-transition recommendations, with acceptance and available-client-control limits.
- `codebase-design/DEEPENING.md`, `DESIGN-IT-TWICE.md`: dependency/test-seam guidance and alternative-interface comparison.
- `diagnose-bugs/scripts/hitl-loop.template.sh`: optional interactive human-loop template with readiness gates; not started automatically.
- `domain-modeling/ADR-FORMAT.md`, `GLOSSARY-FORMAT.md`: fallback formats subordinate to existing conventions and terminology confirmation.
- `improve-codebase-architecture/HTML-REPORT.md`: visual scaffold and diagram patterns; approved artifact location, external browser and offline alternative notes.
- `pr/CREDITS.md`: preserved attribution and pinned HumanLayer source/license review.
- `pr/LICENSE.humanlayer`: full HumanLayer MIT copyright and permission notice for inherited Summary visual guidance; added locally, not an imported Matt resource.
- `prototype/LOGIC.md`, `UI.md`: distinct runnable state exploration and structurally different UI variants; preservation/production limits updated consistently.
- `setup-collection/domain.md`, `issue-tracker-local.md`, `issue-tracker-github.md`, `issue-tracker-gitlab.md`: contextual seed references, no automatic setup or external writes. Upstream triage sections removed; multiline shell examples use body files or verified stdin support.
- `teach/GLOSSARY-FORMAT.md`, `LEARNING-RECORD-FORMAT.md`, `MISSION-FORMAT.md`, `RESOURCES-FORMAT.md`: retained optional formats, used only when saving was requested.
- `writing-for-agents/SKILL-MECHANICS.md`: Codex invocation and chooser guidance.

All original resource paths and hashes are recorded in `upstream-lock.json`.
No selected workflow has a material unresolved dependency on an excluded skill.

## Excluded and overlapping skills

Excluded: `triage`, `tdd`, `implement`, `implement-spec`, `wizard`, and every
unselected upstream skill, including `misc` and `in-progress`. Setup's
`triage-labels.md` and upstream plugin/marketplace installers are omitted.
Needed interview mechanics and architecture survey vocabulary are self-contained.

Other installed collections may expose the same short skill names. Select the
Gonzo Skills entry to use these adaptations; this package does not change other
collections or their activation policies.

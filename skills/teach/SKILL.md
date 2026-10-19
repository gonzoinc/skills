---
name: teach
description: Teach the user a new skill or concept, within this workspace.
---

## Collection policy

Activate this skill only after the user explicitly requests it or accepts a recommendation. Recommendations are allowed; wait for acceptance before activating **any supporting skill**, including from a handoff, note or another skill. Reading a candidate for comparison does not authorize executing it. Skill references below are recommendations, never automatic calls. The user-authorized exception is `post-mortem`: it may automatically record unexpected failures and consult recovery history without activating another workflow.

Follow applicable user and project rules, existing documentation and artifact locations, and the canonical project workspace. Do not create parallel guidance or silently replace existing skills. Use the project's established context sources and normal filesystem tools. Delegate only when authorized and useful.

Put all agent working files in the active project or working folder's primary `.codex/` directory. Remove your temporary scripts, dependencies, captures, logs and intermediates when no longer needed, before reporting completion. Only intended deliverables and maintained project source belong elsewhere. Preserve user-owned and unrelated files; explain any working material retained for unfinished work or reproducibility.

Use short slash names in user-facing recommendations and usage examples, such as `/diagnose-bugs` or `/grilling`; do not require users to type a `gonzo-skills:` prefix. In the desktop app these select skills through the slash menu. Mention the collection name only when needed to distinguish duplicate entries. User acceptance still gates each supporting workflow.

When gathering user input, ask one concise question, optionally give a recommendation, and wait for the answer before asking the next. Do not hide several independent questions inside one sentence or form. Reuse settled answers. This governs the live interview; a requested questionnaire or specification may contain multiple questions or requirements as its deliverable.

Keep secrets out of commands shown to the user and saved artifacts. Use research and browser tools permitted by the active project and user. External publishing and production changes require the applicable user authorization and a concrete reviewable result first. Do not infer that acceptance of this workflow authorizes unrelated writes.

For any user-assisted action, first explain the single action needed, ask whether the user is ready, and stop. Only after explicit readiness request the action and begin dependent capture, monitoring or interactive work. Then stop and wait for completion or the actual result; silence and elapsed time are not completion. Allow adequate time without an arbitrary short timeout.

The user has asked you to teach them something. Teach in the current conversation by default. Use relevant project examples and ask one question at a time, waiting for each answer. Do not assume that a teaching request authorizes saving learning records.

## Teaching Workspace

Use the current project as teaching context. Read existing teaching material when relevant. Create or update learning records, notes, mission files, resources, lessons or reference documents only when the user requests saved material; otherwise deliver the lesson and exercises in the conversation. For saved material, follow existing project locations and formats. The optional layout below applies only when that persistence was requested.

When saved teaching material was requested, workspace paths (`./lessons/` and the rest) resolve from the approved teaching directory; only the `*-FORMAT.md` links resolve from this skill's folder. Existing teaching state may be captured in the following files. The list does not require creating them:

- `MISSION.md`: A document capturing the _reason_ the user is interested in the topic. This should be used to ground all teaching. Use the format in [MISSION-FORMAT.md](./MISSION-FORMAT.md).
- `./reference/*.html`: A directory of reference materials. These are the compressed learnings from the lessons - cheat sheets, reference algorithms, syntax, yoga poses, glossaries. They are the raw units of learning. They should be beautiful documents which print out well, and are designed for quick reference.
- `RESOURCES.md`: A list of resources which can be explored to ground your teaching in contextual knowledge, or to acquire knowledge and wisdom. Use the format in [RESOURCES-FORMAT.md](./RESOURCES-FORMAT.md).
- `./learning-records/*.md`: A directory of learning records, which capture what the user has learned. These are loosely equivalent to architectural decision records in software development - they capture non-obvious lessons and key insights that may need to be revised later, or drive future sessions. These should be used to calculate the zone of proximal development. They are titled `0001-<dash-case-name>.md`, where the number increments each time. Use the format in [LEARNING-RECORD-FORMAT.md](./LEARNING-RECORD-FORMAT.md).
- `./lessons/*.html`: A directory of lessons. A **lesson** is a single, self-contained HTML output that teaches one tightly-scoped thing tied to the mission. This is the primary unit of teaching in this workspace.
- `./assets/*`: Reusable **components** shared across lessons. See [Assets](#assets).
- `NOTES.md`: A scratchpad for you to jot down user preferences, or working notes.

## Philosophy

To learn at a deep level, the user needs three things:

- **Knowledge**, captured from high-quality, high-trust resources
- **Skills**, acquired through highly-relevant interactive lessons devised by you, based on the knowledge
- **Wisdom**, which comes from interacting with other learners and practitioners

Before the `RESOURCES.md` is well-populated, your focus should be to find high-quality resources which will help the user acquire knowledge. Never trust your parametric knowledge.

Some topics may require more skills than knowledge. Learning more about theoretical physics might be more knowledge-based. For yoga, more skills-based.

### Fluency vs Storage Strength

You should be careful to split between two types of learning:

- **Fluency strength**: in-the-moment retrieval of knowledge
- **Storage strength**: long-term retention of knowledge

Fluency can give the user an illusory sense of mastery, but storage strength is the real goal. Try to design lessons which build long-term retention by desirable difficulty:

- Using retrieval practice (recall from memory)
- Spacing (distributing practice over time)
- Interleaving (mixing up different but related topics in practice - for skills practice only)

## Lessons

A lesson is the main unit of teaching. Deliver it conversationally by default, with one exercise or question at a time. When saved lessons were requested, each may be a self-contained HTML file in the established location, using existing numbering conventions.

A lesson should be **beautiful**, with clean, readable typography and layout, since the user will return to these later to review. Think Tufte.

The lesson should be short, and completable very quickly. Learners' working memory is very small, and we need to stay within it. But each lesson should give the user a single tangible win that they can build on. It should be directly tied to the mission, and should be in the user's zone of proximal development.

If possible, open the lesson file for the user by running a CLI command.

Each lesson should link via HTML anchors to other lessons and reference documents.

Each lesson should recommend a primary source for the user to read or watch. This should be the most high-quality, high-trust resource you found on the topic.

Each lesson should contain a reminder to ask followup questions to the agent. The agent is their teacher, and can assist with anything that's unclear.

## Assets

Lessons are built from reusable **components**, stored in `./assets/`: stylesheets, quiz widgets, simulators, diagram helpers, and anything else a second lesson could reuse.

For requested saved HTML lessons, first inspect existing assets in the approved teaching location and reuse suitable components. Add a reusable component there only when the lesson needs it. Conversational teaching creates no asset files.

For a saved course, reuse its shared stylesheet so lessons look consistent. Create a stylesheet only when requested saved lessons need one and no suitable asset exists.

## The Mission

Every lesson should be tied into the mission - the reason that the user is interested in learning about the topic.

If the user is unclear about the mission, or the `MISSION.md` is not populated, your first job should be to question the user on why they want to learn this.

Failing to understand the mission will mean knowledge acquisition is not grounded in real-world goals. Lessons will feel too abstract. You will have no way of judging what the user should do next.

Missions may change as the user develops more skills and knowledge. This is normal - confirm the new mission with the user. Update saved mission files or learning records only when the user requests it.

## Zone Of Proximal Development

Each lesson, the user should always feel as if they are being challenged 'just enough'.

The user may specify an exact thing they want to learn. If they don't, figure out their zone of proximal development by:

- Reading existing relevant learning records, when available, and using answers already given in the conversation
- Figuring out the right thing to teach them based on their mission
- Teach the most relevant thing that fits in their zone of proximal development

## Knowledge

Lessons should be designed around a skill the user is going to learn. The knowledge in the lesson should be only what's required to acquire that skill. You teach the knowledge first, then get the user to practice the skills via an interactive feedback loop.

Knowledge should first be gathered from trusted resources. Cite material claims in the lesson. Use an existing `RESOURCES.md` when relevant; create or update saved resource lists only when requested.

For acquiring knowledge, difficulty is the enemy. It eats working memory you need for understanding.

## Skills

If knowledge is all about acquisition, skills are about durability and flexibility. Make the knowledge stick.

For skill acquisition, difficulty is the tool. Effortful retrieval is what builds storage strength. Skills should be taught through interactive lessons. There are several tools at your disposal:

- Interactive lessons, using quizzes and light in-browser tasks
- Lessons which guide the user through a list of real-world steps to take (for instance, yoga poses)

Each of these should be based on a **feedback loop**, where the user receives feedback on their performance. This feedback loop should be as tight as possible, giving feedback immediately - and ideally automatically.

For quizzes, each answer should be exactly the same number of words (and characters, if possible). Vary which position holds the correct answer across questions. Don't give the user any clues about the answer through formatting or order.

## Acquiring Wisdom

Wisdom comes from true real-world interaction - testing your skills outside the learning environment.

When the user asks a question that appears to require wisdom, your default posture should be to attempt to answer - but to ultimately delegate to a **community**.

A community is a place (online or offline) where the user can test their skills in the real world. This might be a forum, a subreddit, a real-world class (budget permitting) or a local interest group.

You should attempt to find high-reputation communities the user can join. If the user expresses a preference that they don't want to join a community, respect it.

## Reference Documents

When the user requests saved reference material, create reference documents using existing conventions. Lessons can reference these documents - they are useful for tracking raw units of knowledge useful across lessons.

Lessons will rarely be revisited later - reference documents will be. They should be the compressed essence of the lesson, in a format designed for quick reference.

Some learning topics lend themselves to reference:

- Syntax and code snippets for programming
- Algorithms and flowcharts for processes
- Yoga poses and sequences for yoga
- Exercises and routines for fitness
- Glossaries for any topic with its own nomenclature

Glossaries, in particular, are a useful reference. Use the project's established vocabulary in lessons. When a saved teaching glossary is requested and no project format applies, use [GLOSSARY-FORMAT.md](GLOSSARY-FORMAT.md).

## `NOTES.md`

Use teaching preferences expressed in the conversation immediately. Record them in an existing approved `NOTES.md` only when the user asks to save them; otherwise keep them in the conversation.

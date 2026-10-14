# uxblueprint

A portable AI skill for planning user flows, building interfaces in stages, and recording which checks passed, failed, or remain unverified.

Start with the user’s task. Define the flow and design rules, build one useful feature at a time, and keep the verification record with the work. The workflow, references, and templates are bundled in one Markdown file.

## Use the portable file

[uxblueprint-portable.md](uxblueprint-portable.md) contains the complete skill, references, and templates in one Markdown file.

Upload it to an AI tool that accepts Markdown, or paste its contents into the conversation. Then provide your task:

```text
Read uxblueprint-portable.md and follow it for this task:
Redesign the pricing dashboard so users can compare products more easily.
Start with the blueprint only. Do not write application code yet.
```

The tool must be able to read the supplied file. Coding, browser checks, integrations, and deployment depend on that tool's available capabilities and your authorization.

## Choose a mode

| Mode | Example request |
| --- | --- |
| Blueprint only | "Use uxblueprint to plan a bicycle market dashboard. Produce the task flow, design tokens, architecture, and acceptance plan." |
| Guided stages | "Use uxblueprint one stage at a time. Complete the blueprint stage and wait for the next instruction." |
| Build | "Use uxblueprint to implement the approved dashboard in this repository. Complete and verify the applicable stages." |
| Audit or redesign | "Use uxblueprint to audit this interface, prioritize observed friction, and fix the authorized issues." |

If installed as a skill, use the invocation syntax supported by your agent. For agents that support it, an example is `Use $uxblueprint to [task].`

## Use the full skill package

Use your agent's supported skill installer or documented skill-directory convention to install this repository's skill package. Keep its relative paths intact:

- `SKILL.md`: entry point and operating rules.
- `references/`: staged workflow, verification, service-design guidance, prompts, and sources.
- `assets/`: project `AGENTS.md` and blueprint templates, plus an icon.
- `agents/`: optional agent-specific metadata; other tools may ignore it.
- `uxblueprint-portable.md`: self-contained distribution for file-based use.

Read `SKILL.md` first. Adapt the templates to the project; preserve existing project instructions and working behavior.

## Evidence and scope

The workflow distinguishes mockups, prototypes, and connected applications. Completion requires relevant checks and explicit disclosure of unverified behavior; visual polish alone does not establish production readiness.

Service-design guidance is summarized from the supplied textbook chapters. The source textbook PDF is not bundled. Technical sources and provenance are recorded in `references/sources.md`.

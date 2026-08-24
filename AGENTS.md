# CLAUDE.md

This repo holds personal Claude Code skills, distributed via `npx skills add ZhengHe-MD/skills`.

## Adding a skill

1. Create `skills/<skill-name>/SKILL.md` (`<skill-name>`: lowercase, hyphens).
2. Frontmatter needs `name` (matches the directory) and `description` (specific enough to decide, from the description alone, when this skill fires).
3. Use the `writing-for-agents` skill when authoring or editing a `SKILL.md` — it covers frontmatter, invocation choice, and progressive disclosure for any supporting files under the skill's directory.

Keep the flat layout — `skills/<skill-name>/`, no category subfolders — unless the collection grows enough to need them.

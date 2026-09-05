# skills

Personal collection of [Claude Code skills](https://docs.claude.com/en/docs/claude-code/skills) I've created and use regularly.

## Install

Skills here are distributed via [`npx skills`](https://github.com/vercel-labs/skills), which auto-detects your coding agent (Claude Code, Cursor, Codex, etc.) and installs into the right place.

List what's available:

```sh
npx skills add ZhengHe-MD/skills --list
```

Install a specific skill:

```sh
npx skills add ZhengHe-MD/skills --skill <skill-name>
```

Install everything:

```sh
npx skills add ZhengHe-MD/skills --all
```

## Skills

| Skill | Use |
| --- | --- |
| [too-ai](skills/too-ai/SKILL.md) | Rewrite machine-sounding text in plain language without changing its facts. |
| [badminton-video-editing](skills/badminton-video-editing/SKILL.md) | Cut a complete training record or one-clip-per-routine highlights, with no labels. |

## Layout

```
skills/
  <skill-name>/
    SKILL.md
```

Each skill lives in its own directory under `skills/` with a `SKILL.md` describing what it does and how to use it.

## Contributing

These are personal skills, tuned to how I work. Feel free to fork and adapt.

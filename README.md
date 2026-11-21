# no-slop-skills

Agent skills that keep AI output from looking like slop.

## Install

### Universal (Antigravity, Claude Code, Codex, Cursor, Gemini CLI, etc.)

```bash
npx skills add rickyrobinett/no-slop-skills
```

To install a single skill:

```bash
npx skills add rickyrobinett/no-slop-skills --skill no-slop-slides
```

### Claude Code Plugin Marketplace

```text
/plugin marketplace add rickyrobinett/no-slop-skills
/plugin install no-slop-skills@no-slop-skills
```

### Manual (Antigravity / Codex / Gemini CLI)

Copy any folder from `skills/` into your project's `.agents/skills/` directory (or `~/.agents/skills/` globally).

## Skills

| Skill | What it does | Origin |
| --- | --- | --- |
| [`no-slop-slides`](skills/no-slop-slides/SKILL.md) | Keeps AI-generated slide decks focused on story, readability (30pt+ font), real visuals, and clean layouts instead of wordy slop. | [ricky.robinett.ai/noslopslides](https://ricky.robinett.ai/noslopslides) |

## Contributing

Have a lesson learned or a skill that keeps AI output sharp and human? See [CONTRIBUTING.md](CONTRIBUTING.md) and open a PR.

## License

[MIT](LICENSE)

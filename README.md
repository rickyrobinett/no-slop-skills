# no-slop-skills

Agent skills that keep AI output from looking like slop.

## Install

**Fastest path — any agent, one command** (Antigravity, Claude Code, Codex, Cursor, Gemini CLI, and more):

```bash
npx skills add rickyrobinett/no-slop-skills
```

To install a single skill:

```bash
npx skills add rickyrobinett/no-slop-skills --skill no-slop-slides
```

Prefer a native tool integration? Pick your tool below.

<details>
<summary><b>Claude Code</b></summary>

```text
/plugin marketplace add rickyrobinett/no-slop-skills
/plugin install no-slop-skills@no-slop-skills
```

> **SSH errors?** If you don't have SSH keys configured on GitHub, use the HTTPS URL instead:
> ```text
> /plugin marketplace add https://github.com/rickyrobinett/no-slop-skills.git
> /plugin install no-slop-skills@no-slop-skills
> ```

</details>

<details>
<summary><b>Antigravity CLI</b></summary>

```bash
agy plugin install https://github.com/rickyrobinett/no-slop-skills.git
```

</details>

<details>
<summary><b>Gemini CLI</b></summary>

```bash
gemini skills install https://github.com/rickyrobinett/no-slop-skills.git --path skills
```

</details>

<details>
<summary><b>Manual (Codex / Cursor / local copy)</b></summary>

Copy any folder from `skills/` into your project's `.agents/skills/` directory (or `~/.agents/skills/` globally).

</details>

## Skills

| Skill | What it does | Origin |
| --- | --- | --- |
| [`no-slop-slides`](skills/no-slop-slides/SKILL.md) | Keeps AI-generated slide decks focused on story, readability (30pt+ font), real visuals, and clean layouts instead of wordy slop. | [ricky.robinett.ai/noslopslides](https://ricky.robinett.ai/noslopslides) |

## Contributing

Have a lesson learned or a skill that keeps AI output sharp and human? See [CONTRIBUTING.md](CONTRIBUTING.md) and open a PR.

## License

[MIT](LICENSE)

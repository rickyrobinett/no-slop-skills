# no-slop-skills

A collection of [Agent Skills](https://agentskills.io) (`SKILL.md` instruction files) that give AI coding agents concrete rules for tasks like slide decks and `README.md` files. Works with Antigravity CLI, Claude Code, Codex, Cursor, and other tools that support the Agent Skills format.

## Quick Start

Install all skills (requires Node.js):

```bash
npx skills add rickyrobinett/no-slop-skills
```

Then invoke a skill in your agent with a prompt (or let it trigger automatically on a matching task):

```text
Use the no-slop-readme skill to review and rewrite this repository's README.md.
```

To install a single skill instead of the full collection:

```bash
npx skills add rickyrobinett/no-slop-skills --skill no-slop-readme
```

### Other installation methods

<details>
<summary><b>Claude Code</b></summary>

Run inside Claude Code:

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
<summary><b>Manual (Codex / Cursor / local copy)</b></summary>

Copy any folder from `skills/` into your project's `.agents/skills/` directory (or `~/.agents/skills/` globally).

</details>

## Skills

| Skill | What it does |
| --- | --- |
| [`no-slop-slides`](skills/no-slop-slides/SKILL.md) | Enforces narrative arc, standalone story headers, 30pt+ minimum font size, real visuals, and digital-twin review for slide decks. |
| [`no-slop-readme`](skills/no-slop-readme/SKILL.md) | Enforces concise project descriptions, quick-start samples or prompts, verified technical accuracy and casing, and adversarial digital-twin review for `README.md` files. |

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines on adding a new skill or improving an existing one.

## License

[MIT](LICENSE)

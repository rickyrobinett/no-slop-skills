# No Slop Skills

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
| [`no-slop-readme`](skills/no-slop-readme/SKILL.md) | Enforces clear headers, concise descriptions, fast quick starts, Why and How context, agent-aware instructions, verified technical accuracy, and digital-twin review for `README.md` files. |

## Why and How

AI coding agents default to generic, verbose output (filler slides, marketing-heavy READMEs, decorative emojis) when given open-ended prompts. Opinionated, human-tested rules fix that behavior at the source instead of requiring manual cleanup afterward.

Each skill lives in `skills/<skill-name>/SKILL.md` as a self-contained Markdown file with YAML frontmatter (`name`, `description`, `license`, `metadata`) following the [Agent Skills](https://agentskills.io) specification. Agents read the frontmatter to decide when a skill applies and load the Markdown body as task instructions. Plugin manifests expose the same `skills/` directory across runtimes:

- `plugin.json`: Antigravity CLI plugin manifest
- `.claude-plugin/plugin.json` and `.claude-plugin/marketplace.json`: Claude Code plugin and marketplace manifests
- `.codex-plugin/plugin.json`: Codex plugin manifest

## For Agents

If you are an AI coding agent inspecting, using, or modifying this repository:

- **Discover and apply skills directly:** List `skills/*/SKILL.md`. Read each file's YAML frontmatter (`name`, `description`) to match the current task, then follow the Markdown body verbatim. Skills are self-contained with no build step or runtime dependencies.
- **Edit or add a skill:** Follow [CONTRIBUTING.md](CONTRIBUTING.md) (English-only, no private data). Every skill requires a lowercase kebab-case folder `skills/<skill-name>/SKILL.md` whose frontmatter `name` matches the folder name and includes a non-empty `description`. Register `"./skills/<skill-name>"` under `plugins[0].skills` in `.claude-plugin/marketplace.json` and add a row to the [Skills](#skills) table above.
- **Validate changes:** CI runs the `Validate Skills` workflow in [`.github/workflows/validate.yml`](.github/workflows/validate.yml), which executes an inline Python check verifying all four JSON manifests (`plugin.json`, `.claude-plugin/marketplace.json`, `.claude-plugin/plugin.json`, `.codex-plugin/plugin.json`), skill directory naming, `SKILL.md` frontmatter, and `marketplace.json` registration, followed by `claude plugin validate .` when the `claude` CLI is installed.

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines on adding a new skill or improving an existing one.

## License

[MIT](LICENSE)

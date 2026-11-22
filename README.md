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
| [`no-slop-readme`](skills/no-slop-readme/SKILL.md) | Enforces clear headers, concise descriptions, fast quick starts, Show and Tell visuals, agent-aware docs, verified technical accuracy, and digital-twin review for `README.md` files. |

## Why and How

AI coding agents default to generic, verbose output (filler slides, marketing-heavy READMEs, decorative emojis) when given open-ended prompts. Opinionated, human-tested rules fix that behavior at the source instead of requiring manual cleanup afterward.

Each skill lives in `skills/<skill-name>/SKILL.md` as a self-contained Markdown file with YAML frontmatter (`name`, `description`, `license`, `metadata`) following the [Agent Skills](https://agentskills.io) specification. Agents match the frontmatter automatically (or when named in a prompt), load the Markdown body as task instructions, and run a digital-twin review before finalizing output:

```text
  Install            Match               Apply                Review & output
+------------+     +-------------+     +--------------+     +-----------------+
| npx skills | --> | Agent reads | --> | Loads        | --> | Digital-twin    |
| or plugin  |     | frontmatter |     | SKILL.md     |     | review -> final |
+------------+     +-------------+     +--------------+     +-----------------+
```

### Repository layout

```text
no-slop-skills/
├── skills/
│   ├── no-slop-readme/SKILL.md     # README rules (YAML frontmatter + body)
│   └── no-slop-slides/SKILL.md     # Slide deck rules
├── plugin.json                     # Antigravity CLI manifest
├── .claude-plugin/
│   ├── plugin.json                 # Claude Code plugin manifest
│   └── marketplace.json            # Claude Code marketplace index
├── .codex-plugin/
│   └── plugin.json                 # Codex plugin manifest
└── .github/workflows/validate.yml  # CI manifest & frontmatter validator
```

### Runtime compatibility

The same `skills/` directory is exposed across agent runtimes through their respective manifests:

| Runtime | Manifest | Install method |
| --- | --- | --- |
| Antigravity CLI | `plugin.json` | `agy plugin install` or `npx skills add` |
| Claude Code | `.claude-plugin/plugin.json`, `.claude-plugin/marketplace.json` | `/plugin marketplace add` or `npx skills add` |
| Codex | `.codex-plugin/plugin.json` | `npx skills add` or manual copy to `.agents/skills/` |
| Cursor and other Agent Skills tools | `skills/*/SKILL.md` | `npx skills add` or manual copy to `.agents/skills/` |

## For Agents

If you are an AI coding agent inspecting, using, or modifying this repository:

- **Discover and apply skills directly:** List `skills/*/SKILL.md`. Read each file's YAML frontmatter (`name`, `description`) to match the current task, then follow the Markdown body verbatim. Skills are self-contained with no build step or runtime dependencies.
- **Edit or add a skill:** Follow [CONTRIBUTING.md](CONTRIBUTING.md) (English-only, no private data). Every skill requires a lowercase kebab-case folder `skills/<skill-name>/SKILL.md` whose frontmatter `name` matches the folder name and includes a non-empty `description`. Register `"./skills/<skill-name>"` under `plugins[0].skills` in `.claude-plugin/marketplace.json`, then update the [Skills](#skills) table and [Repository layout](#repository-layout) above.
- **Validate changes:** CI runs the `Validate Skills` workflow in [`.github/workflows/validate.yml`](.github/workflows/validate.yml), which executes an inline Python check verifying all four JSON manifests (`plugin.json`, `.claude-plugin/marketplace.json`, `.claude-plugin/plugin.json`, `.codex-plugin/plugin.json`), skill directory naming, `SKILL.md` frontmatter, and `marketplace.json` registration, followed by `claude plugin validate .` when the `claude` CLI is installed.

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines on adding a new skill or improving an existing one.

## License

[MIT](LICENSE)

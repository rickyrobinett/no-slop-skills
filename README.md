# No Slop Skills

[![Validate Skills](https://github.com/rickyrobinett/no-slop-skills/actions/workflows/validate.yml/badge.svg)](https://github.com/rickyrobinett/no-slop-skills/actions/workflows/validate.yml)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)

[Agent Skills](https://agentskills.io) (`SKILL.md` instruction files) that give AI coding agents concrete rules for slide decks and `README.md` files. Works with Antigravity CLI, Claude Code, Codex, Cursor, and other tools that support the Agent Skills standard.

## Quick Start

### With the CLI

Install with the [Skills CLI](https://skills.sh) (requires Node.js):

```bash
npx skills add rickyrobinett/no-slop-skills                        # all skills
npx skills add rickyrobinett/no-slop-skills --skill no-slop-readme # single skill
```

Then run a skill in your agent (or let it trigger automatically on a matching task):

```text
Use the no-slop-readme skill to review and rewrite this repository's README.md.
```

### With a prompt (no terminal required)

Paste this into Claude Code, Cursor, Codex, or Antigravity CLI to install and run a skill in one step:

```text
Install the skills from https://github.com/rickyrobinett/no-slop-skills, then use the no-slop-readme skill to review and rewrite my README.md.
```

For slide decks, replace `no-slop-readme` with `no-slop-slides`.

### Other installation methods

<details>
<summary><b>Claude Code</b></summary>

Run inside Claude Code:

```text
/plugin marketplace add rickyrobinett/no-slop-skills
/plugin install no-slop-skills@no-slop-skills
```

> **SSH errors?** Use the HTTPS URL instead:
>
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

Clone this repository and copy any folder from `skills/` into your project's `.agents/skills/` directory (or `~/.agents/skills/` globally).

</details>

## Skills

| Skill | Applies to | Key rules |
| --- | --- | --- |
| [`no-slop-slides`](skills/no-slop-slides/SKILL.md) | Slide decks | Narrative arc, standalone headers, 30pt+ font, real visuals, digital-twin review |
| [`no-slop-readme`](skills/no-slop-readme/SKILL.md) | `README.md` files | Fast quick start, user focus, verified accuracy, restrained badges, digital-twin review |

## Why and How

AI agents default to generic, padded output on slide decks and READMEs unless given explicit constraints. Each skill in this repository packages concrete rules into a single Markdown file (`skills/<skill-name>/SKILL.md`) with no build step or runtime dependencies.

The Skills CLI reads `skills/` directly, and four plugin manifests expose those same files to Antigravity CLI, Claude Code, and Codex. On every push and pull request, [`.github/workflows/validate.yml`](.github/workflows/validate.yml) validates all manifests and skill files.

### Repository layout

```text
no-slop-skills/
├── skills/
│   ├── no-slop-readme/SKILL.md     # README rules
│   └── no-slop-slides/SKILL.md     # Slide deck rules
├── plugin.json                     # Antigravity CLI manifest
├── .claude-plugin/
│   ├── plugin.json                 # Claude Code plugin manifest
│   └── marketplace.json            # Claude Code marketplace index
├── .codex-plugin/
│   └── plugin.json                 # Codex plugin manifest
└── .github/workflows/validate.yml  # CI manifest & frontmatter validator
```

## For Agents

### Discover and apply skills

- List `skills/*/SKILL.md` and read each file's YAML frontmatter (`name`, `description`) to match the current task.
- Follow the Markdown body verbatim.

### Edit or add a skill

Follow [CONTRIBUTING.md](CONTRIBUTING.md) (English-only, no private data):

1. Create `skills/<skill-name>/SKILL.md` using a lowercase kebab-case folder name.
2. Set YAML frontmatter `name` to match the folder name and include a non-empty `description`.
3. Register `"./skills/<skill-name>"` under `plugins[0].skills` in `.claude-plugin/marketplace.json`.
4. Update the [Skills](#skills) table and [Repository layout](#repository-layout) above.

### Validate changes

Run `claude plugin validate .` locally if the `claude` CLI is installed. On push and pull request, [`.github/workflows/validate.yml`](.github/workflows/validate.yml) checks:

- All four JSON manifests (`plugin.json`, `.claude-plugin/marketplace.json`, `.claude-plugin/plugin.json`, `.codex-plugin/plugin.json`).
- Kebab-case skill folder names, `SKILL.md` frontmatter (`name`, `description`), and `marketplace.json` registration.

## Resources

- [Please, no more AI slop slides](https://ricky.robinett.ai/noslopslides) — original guide and slide template behind `no-slop-slides`
- [Agent Skills Specification](https://agentskills.io) — open format used by `skills/*/SKILL.md`
- [Skills CLI (`skills.sh`)](https://skills.sh) — CLI installer for Agent Skills

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md) to add a skill or improve an existing one.

## License

[MIT](LICENSE)

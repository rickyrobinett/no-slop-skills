# No Slop Skills

A collection of [Agent Skills](https://agentskills.io) (`SKILL.md` instruction files) that give AI coding agents concrete rules for tasks like slide decks and `README.md` files. Works with Antigravity CLI, Claude Code, Codex, Cursor, and other tools that support the Agent Skills standard.

## Quick Start

Install with the [Skills CLI](https://skills.sh) (requires Node.js):

```bash
npx skills add rickyrobinett/no-slop-skills                        # all skills
npx skills add rickyrobinett/no-slop-skills --skill no-slop-readme # single skill
```

Then invoke a skill in your agent (or let it trigger automatically on a matching task):

```text
Use the no-slop-readme skill to review and rewrite this repository's README.md.
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
| [`no-slop-readme`](skills/no-slop-readme/SKILL.md) | `README.md` files | Fast quick start, verified accuracy, clean layout, agent instructions, digital-twin review |

## Why and How

AI coding agents default to generic, verbose output (filler slides, marketing-heavy READMEs, decorative emojis) when given open-ended prompts. Opinionated, human-tested rules fix that behavior at the source instead of requiring manual cleanup afterward.

### How skills work

Each skill is a self-contained `skills/<skill-name>/SKILL.md` file following the [Agent Skills](https://agentskills.io) specification:

1. **Discover:** Agents read the YAML frontmatter (`name`, `description`) to match a task automatically, or activate a skill when named in a prompt.
2. **Execute:** Agents load the Markdown body as task instructions.
3. **Review:** Skills include a digital-twin review pass before finalizing output.

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

## For Agents

If you are an AI coding agent inspecting, using, or modifying this repository:

### Discover and apply skills

- List `skills/*/SKILL.md` and read each file's YAML frontmatter (`name`, `description`) to match the current task.
- Follow the Markdown body verbatim. Skills have no build step or runtime dependencies.

### Edit or add a skill

Follow [CONTRIBUTING.md](CONTRIBUTING.md) (English-only, no private data):

1. Create `skills/<skill-name>/SKILL.md` using a lowercase kebab-case folder name.
2. Set YAML frontmatter `name` to match the folder name and include a non-empty `description`.
3. Register `"./skills/<skill-name>"` under `plugins[0].skills` in `.claude-plugin/marketplace.json`.
4. Update the [Skills](#skills) table and [Repository layout](#repository-layout) above.

### Validate changes

CI runs `Validate Skills` ([`.github/workflows/validate.yml`](.github/workflows/validate.yml)) on pushes and pull requests:

- Checks all four JSON manifests: `plugin.json`, `.claude-plugin/marketplace.json`, `.claude-plugin/plugin.json`, and `.codex-plugin/plugin.json`.
- Verifies skill folder naming, `SKILL.md` frontmatter, and `marketplace.json` registration.
- Runs `claude plugin validate .` when the `claude` CLI is installed (run it locally too if available).

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines on adding a new skill or improving an existing one.

## License

[MIT](LICENSE)

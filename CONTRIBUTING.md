# Contributing

Have a lesson learned or a skill that keeps AI output sharp, useful, and human? Open a PR.

## Before proposing a new skill

1. **Check the catalog and open PRs.** Browse the skills table in [README.md](README.md) and open PRs first so we avoid duplicates.
2. **Prefer extending over duplicating.** If your idea strengthens an existing skill, open a focused PR against that skill instead of adding a near-duplicate.

## What makes a good no-slop skill

- **Opinionated and concrete.** Give agents specific constraints they can actually follow (like a 30pt minimum font size or standalone story headers), not vague advice like "make it engaging."
- **Concise.** Keep `SKILL.md` tight. If a rule can be said in one sentence, don't write a paragraph.
- **Battle-tested.** Share rules that came from real work where AI output fell short and a concrete constraint fixed it.
- **No private data.** Never include internal links, credentials, or personal info.

## Adding a new skill

1. Create a folder under `skills/<skill-name>/` using lowercase kebab-case (e.g., `skills/no-slop-slides/`).
2. Add `skills/<skill-name>/SKILL.md` with standard [Agent Skills](https://agentskills.io) frontmatter:

   ```yaml
   ---
   name: <skill-name>
   description: >
     Clear description of what the skill does and when an agent should trigger it.
   license: MIT
   metadata:
     author: Your Name
     version: "1.0.0"
   ---
   ```

   `name` must match the directory name.
3. Add `"./skills/<skill-name>"` to `plugins[0].skills` in `.claude-plugin/marketplace.json`.
4. Add a row to the Skills table in `README.md`.
5. Open a pull request describing what slop pattern the skill prevents and how you've tested it.

## Improving an existing skill

PRs that tighten wording, add sharp examples, or fix edge cases are always welcome.

## Language

Keep all skills and documentation in **English only**. Translated copies drift out of sync as skills evolve, so we do not accept translation PRs.

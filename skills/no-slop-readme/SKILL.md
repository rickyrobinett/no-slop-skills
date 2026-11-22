---
name: no-slop-readme
description: >
  Write, edit, and review project README files that get readers to hello world
  fast without AI slop, marketing fluff, or decorative emojis. Use whenever
  creating, rewriting, or reviewing a README.md for a repository, library, CLI,
  or open source project. Enforces concise project descriptions, quick-start
  code samples or prompts, verified technical accuracy and casing, and
  adversarial digital-twin review.
license: MIT
metadata:
  author: Ricky Robinett
  version: "4.0.0"
---

# No Slop README

## Overview

A good README typically follows the following format:

- **Header:** This is the name of your project. Don't copy straight from repo slug, use the actual name (e.g., `no-slop-skills` vs `No Slop Skills`).
- **A description of the project:** Keep this concise, 1–3 sentences max. And avoid marketing jargon and hyperbole.
- **Quick Start:** Many readers make it to your repository already knowing they want to use it; help them get started as quickly as possible.
- **The Why and How:** Especially in the world of agents consuming content, it's helpful to describe why a repo exists and how it works.
- **Contribution Guide, Team:** If needed, provide a contribution guide and team highlights.
- **License:** So readers know what they can and can't do with this code.

## What to do

### Time to Hello World

A README should help get a reader to hello world as quickly as possible. Prominently feature any needed code samples, or copy/pasteable prompts early on in the README. While further sections in the README may focus on more detailed configuration and setup, make the initial setup as quick and straightforward as possible.

### Technical Accuracy

Validate that any statements made within the README are technically accurate and verified. Ensure that casing and spacing are correct (e.g., php vs PHP, agent skills vs AgentSkills vs Agent Skills). If in doubt about any portion of the README, go back to the user to ask questions and verify.

### Show and Tell

When relevant, don't just describe the repository but show the user visually (using tables, ASCII charts, demo gifs, properly highlighted and formatted code highlighting) including the file structure or workflows. Don't overdo this though, only add a visual display if it meaningfully improves the understanding a reader would have of the repo or how it works.

### Agent Aware

When relevant, provide instructions for not only humans but agents to use your project. And make sure the README provides agents anything they'd need to understand and use this repository.

### Adversarial Reviewers

After completing a README draft, run a review pass with digital twins of target users of various skill levels to give feedback on understandability, usability and to help refine.

## What to avoid

### Marketing fluff, jargon and hyperbole

Readers are here to be empowered, not marketed to. Ensure the README is focused on the user's needs and avoid statements like "easiest", "best" or buzzword soup.

### Emojis

Use emojis only if they directly relate to what the README is helping a user accomplish.

## Sample Repos

Here are some sample repos with READMEs I like. Examine them for inspiration and insight:

- https://github.com/addyosmani/agent-skills
- https://github.com/langchain-ai/langchain
- https://github.com/redis/redis

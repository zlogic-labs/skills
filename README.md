# Agent Skills

Reusable **Agent Skills for AI coding agents and AI assistants**.

This repository provides small, focused `SKILL.md` instruction sets for tasks such as **UI design, UX review, technical writing, and human-centered writing**. Skills are designed to work with skills-compatible agents and can be reused across projects.

## Skills

### [`design-guide`](./design-guide/)

An **AI UI design and UX review skill** for creating cleaner, more consistent interfaces.

It guides AI agents through:

* UI hierarchy and visual structure
* Layout, spacing, and composition
* Interaction and usability
* Visual consistency and component reuse
* Design review and refinement
* Avoiding unnecessary UI elements and visual clutter

Use it when asking an AI coding agent to **design, review, refine, or implement a user interface**.

### [`human-writing`](./human-writing/)

A **writing skill for AI agents** that helps produce clear, specific, natural-sounding text without generic AI filler.

It covers:

* User-facing product copy
* Technical writing
* Documentation
* UI text and microcopy
* Rewriting and editing
* Translation and localization
* Avoiding repetitive or artificial AI writing patterns

Use it when an AI agent needs to **write, rewrite, translate, or polish text**.

### [`skill-writer`](./skill-writer/)

An **Agent Skill for authoring Agent Skills** — turning requirements, notes, workflows, or postmortems into an executable `SKILL.md`.

It covers:

* The frontmatter contract a `SKILL.md` must satisfy — `name`, `description`, and the body size threshold
* Extracting one current workflow from raw source material
* Writing every step as action, verification, and recovery
* Marking user confirmation points, unusable states, and hard constraints
* Compressing away debugging history, background, and duplicated rules
* Simulating execution to find every point where an Agent would have to guess

Use it when an AI agent needs to **write, restructure, or trim a Skill**.

## Why Agent Skills?

Agent Skills are reusable instruction sets that extend the capabilities of AI agents without embedding task-specific rules directly into a project prompt.

Each skill is a self-contained directory with a `SKILL.md` file containing YAML frontmatter and instructions. A compatible agent can discover the skill and load it when its description matches the current task.

This makes skills:

* **Reusable** across projects
* **Version-controlled** with Git
* **Portable** between compatible AI agents
* **Focused** on a specific task or workflow
* **Composable** with other agent skills

The goal is not to make agents generate more. It is to help them make better decisions about **what to do and what not to do**.

## Installation

The easiest way to install a skill from this repository is with the [Skills CLI](https://github.com/vercel-labs/skills):

```bash
npx skills add zlogic-labs/skills
```

Install a specific skill:

```bash
npx skills add zlogic-labs/skills --skill design-guide
```

```bash
npx skills add zlogic-labs/skills --skill human-writing
```

Install all skills:

```bash
npx skills add zlogic-labs/skills --all
```

You can also install the skills manually by copying or symlinking them into the directory used by your AI agent.

For example, agents using the shared `.agents/skills` location can use:

```bash
ln -s "$PWD/design-guide" ~/.agents/skills/design-guide
ln -s "$PWD/human-writing" ~/.agents/skills/human-writing
```

Claude Code uses its own skill directory:

```bash
ln -s "$PWD/design-guide" ~/.claude/skills/design-guide
ln -s "$PWD/human-writing" ~/.claude/skills/human-writing
```

Other AI coding agents may use different skill directories.

## Supported AI Agents

Agent Skills are designed for compatible AI coding agents and AI assistants.

Depending on the agent, skills can be installed into agent-specific directories such as:

* Claude Code
* Codex
* Cursor
* GitHub Copilot
* Gemini CLI
* OpenCode
* Other Agent Skills-compatible tools

Installation paths vary by agent. Use the agent's documentation or the Skills CLI to install skills automatically.

## How Skills Work

A skill is a directory containing a `SKILL.md` file:

```text
design-guide/
└── SKILL.md
```

The file contains YAML frontmatter such as:

```yaml
---
name: design-guide
description: Guidelines for AI agents designing and reviewing user interfaces.
---
```

The `description` helps an AI agent determine when the skill is relevant. The agent then loads the skill instructions when the task matches its intended use.

Skills can also include supporting files such as:

```text
skill-name/
├── SKILL.md
├── references/
├── scripts/
└── assets/
```

Only add supporting files when they are needed by the skill.

## Design Philosophy

The skills in this repository share a simple principle:

> When something looks unfinished, don't automatically add another card, badge, section, or paragraph. Fix the underlying problem first.

Good agent behavior is not about producing more output. It is about making better decisions, preserving hierarchy, and knowing when **not** to add something.

## Repository Structure

```text
skills/
├── design-guide/
│   └── SKILL.md
├── human-writing/
│   └── SKILL.md
├── skill-writer/
│   ├── SKILL.md
│   └── README.md
├── LICENSE
└── README.md
```

Each skill is independent and can be installed without installing the rest of the repository.

## Contributing

To add a new Agent Skill:

1. Create a top-level directory for the skill.
2. Add a `SKILL.md` with YAML frontmatter.
3. Give the skill a specific `name` and `description`.
4. Keep the skill focused on a well-defined task or workflow.
5. Add supporting references, scripts, or assets only when necessary.

The `description` should clearly explain **what the skill does and when an AI agent should use it**.

## License

Apache License 2.0
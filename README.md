# skills

[![License: Apache 2.0](https://img.shields.io/badge/License-Apache_2.0-blue.svg)](LICENSE)

Reusable instructions for AI coding agents — the rules that decide what gets written and what gets built, written down so every session follows the same standard.

These are not prompts to paste into a chat window. They are [skills](https://code.claude.com/docs/en/skills): folders with a `SKILL.md` that the agent loads when the task matches its description, then follows.

## Skills

| Skill | What it does | Use it when |
|---|---|---|
| [design-guide](design-guide/SKILL.md) | Design rules for UI. Solve information, hierarchy, layout, and interaction first, decoration last. Reuse the project's existing components, tokens, and icons. | Designing or reviewing a screen, choosing a layout, deciding whether something needs a card, border, shadow, or icon. |
| [human-writing](human-writing/SKILL.md) | Writing rules. Remove filler, hype, padding, and manufactured tone. Prefer concrete facts. Never invent personal experience. | Writing or rewriting anything user-facing — replies, docs, issues, PR text, commits, translations. |

Both skills share one stance: the default answer to "this looks empty / unfinished / not thorough enough" is to leave it alone, not to add another card, badge, or paragraph.

## Install

Skills are plain folders. Put each one where your agent looks for skills — symlink it if you want to keep editing this checkout, copy it if you want a frozen copy.

The shared location is `~/.agents/skills/<name>/`. Agents that read it — [zlogic](https://zlogic.run), Codex, and others — pick these skills up from there.

```bash
ln -s "$PWD/design-guide"  ~/.agents/skills/design-guide
ln -s "$PWD/human-writing" ~/.agents/skills/human-writing
```

Claude Code uses its own directory instead, `~/.claude/skills/<name>/` for personal and `.claude/skills/<name>/` per project. Link there too if you use it:

```bash
ln -s "$PWD/design-guide"  ~/.claude/skills/design-guide
ln -s "$PWD/human-writing" ~/.claude/skills/human-writing
```

Both at once is fine — the agent only reads the folder. See [Skills in Claude Code](https://code.claude.com/docs/en/skills) for that client's specifics.

Restart the agent after installing. The skill loads on its own when a task matches its description; type `/` to invoke it by name.

## Layout

```text
skills/
├── design-guide/
│   └── SKILL.md      26 rules: hierarchy, restraint, reuse, review checklist
├── human-writing/
│   └── SKILL.md      21 rules: filler, specificity, voice, translation, final check
├── LICENSE
└── README.md
```

Each `SKILL.md` starts with YAML frontmatter carrying `name` and `description`. The description is what the agent matches against, so it holds the trigger conditions; the body is what it follows once loaded.

## Contributing

Add a skill as a top-level folder with its own `SKILL.md`. Keep the description specific — it decides when the skill fires.

The rule when editing these files: describe the behavior, don't restate it. If a section can be deleted without losing a constraint, delete it.

## License

[Apache License 2.0](LICENSE)
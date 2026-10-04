# design-guide

An Agent Skill for **AI coding agents designing, implementing, or reviewing UI/UX**.

It helps AI agents make better interface decisions around **layout, hierarchy, typography, spacing, components, interaction patterns, and visual noise** — without adding unnecessary UI, and by validating uncertain designs with a throwaway prototype before writing the final interface.

```bash
npx skills add zlogic-labs/skills --skill design-guide
```

Or symlink it into your agent's skills directory:

```bash
ln -s "$PWD/design-guide" ~/.agents/skills/design-guide
```

The full instructions are in [`SKILL.md`](./SKILL.md). Compatible agents load the skill when its description matches the task.

## What it covers

| Rules | Topic                                                                                           |
| ----- | ----------------------------------------------------------------------------------------------- |
| 1–2   | Understand the task and establish hierarchy through position, spacing, typography, and contrast |
| 3–5   | Use cards, borders, and backgrounds only when they communicate structure or meaning             |
| 6–8   | Use icons when they add meaning; prefer the project's existing icon library                     |
| 9–13  | Keep badges, radius, shadows, whitespace, and visual noise intentional                          |
| 14–15 | Follow familiar UI patterns instead of defaulting to dashboards                                 |
| 16–20 | Reuse existing components, design tokens, and the project's design system                       |
| 21–23 | Don't add unrequested features; prioritize content and information structure                    |
| 24    | Avoid common AI-generated UI patterns such as card + icon + background and nested containers    |
| 25    | Follow the design decision process and validate uncertain designs with a prototype             |
| 26    | Review the result and remove elements that don't improve clarity or function                    |

## The short version

**Fix the information structure first.**

A card, badge, icon, border, or shadow that carries no meaning is noise. Adding visual elements just because a page feels empty usually makes the interface worse.

The skill favors **clear hierarchy, familiar interaction patterns, restraint, component reuse, and purposeful visual design** over decorative UI.

When a layout, information architecture, or interaction is genuinely uncertain, it **prototypes before implementing** — one disposable HTML file, realistic content, then the user's review. Showing a prototype is not the same as getting it approved.

Full rationale and examples are in [`SKILL.md`](./SKILL.md).

## License

Apache License 2.0 — see [`LICENSE`](../LICENSE).
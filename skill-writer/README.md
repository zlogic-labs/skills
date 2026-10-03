# skill-writer

An Agent Skill for **AI agents writing, restructuring, or trimming other Agent Skills**.

It turns requirements, notes, workflows, postmortems, or an existing `SKILL.md` into an **executable workflow** — the smallest set of instructions an Agent needs to complete the task correctly.

```bash
npx skills add zlogic-labs/skills --skill skill-writer
```

Or symlink it into your agent's skills directory:

```bash
ln -s "$PWD/skill-writer" ~/.agents/skills/skill-writer
```

The full instructions are in [`SKILL.md`](./SKILL.md). Compatible agents load the skill when its description matches the task.

## What it covers

| Step | Topic                                                                                          |
| ---- | ---------------------------------------------------------------------------------------------- |
| 1    | Lock the contract: directory, `name`/`description` rules, and what discovery actually depends on  |
| 2    | Collect source material from existing project artifacts before asking the user                  |
| 3    | Reduce the source to one current workflow; never guess between competing approaches             |
| 4    | Write each step as action → verify → recover, using real commands, paths, and arguments         |
| 5    | Mark user confirmation points, unusable states, and hard constraints                            |
| 6    | Compress in three passes: history, non-executable content, duplication                         |
| 7    | Simulate execution and fix every point where the Agent would have to guess                      |
| 8    | Validate content and size (500 lines / ~5k tokens), then report without the edit log           |

## The short version

**Write what the Agent must do now, not how someone eventually figured out what to do.**

A Skill is an execution guide, not documentation, a knowledge base, or a postmortem. Anything that does not change what the Agent does, avoids, verifies, stops for, or recovers from gets deleted — including the story of how the solution was found, and including a rule that the correct workflow already makes impossible to violate.

The `description` is the only part loaded before a skill triggers, so all "when to use this" information belongs there. The body is instructions and nothing else.

The goal is the **minimum reliable execution procedure**: every step concrete, every important action verifiable next to it, every known failure recoverable.

Full rationale and examples are in [`SKILL.md`](./SKILL.md).

## License

Apache License 2.0 — see [`LICENSE`](../LICENSE).
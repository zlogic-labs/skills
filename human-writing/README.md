# human-writing

An Agent Skill for **AI agents writing, rewriting, editing, or translating text**.

It helps AI agents produce **natural, clear, specific, human-sounding writing** for technical documentation, product copy, UI text, developer communication, and other user-facing content.

```bash id="q5v8ne"
npx skills add zlogic-labs/skills --skill human-writing
```

Or symlink it into your agent's skills directory:

```bash id="r2m6cx"
ln -s "$PWD/human-writing" ~/.agents/skills/human-writing
```

The full instructions are in [`SKILL.md`](./SKILL.md). Compatible agents load the skill when its description matches the task.

## What it covers

| Rules | Topic                                                                                                        |
| ----- | ------------------------------------------------------------------------------------------------------------ |
| 1–3   | Match the context, skip what the reader already knows, and remove generic AI filler                          |
| 4–6   | Prefer concrete language, concise writing, and specific information over vague claims or hype                |
| 7–9   | Avoid manufactured balance, repetitive list structures, and monotonous sentence patterns                     |
| 10–11 | Preserve the author's voice and match the appropriate tone to the context                                    |
| 12–14 | Technical writing, product copy, UI text, documentation, and developer communication                         |
| 15–18 | Avoid invented experience, manufactured emotion, obvious explanations, and empty conclusions                 |
| 19–20 | Translate meaning rather than sentences; rewrite without unnecessarily changing the author's intent or voice |
| 21    | Final review for AI patterns, information density, specificity, voice, simplicity, and naturalness           |

## The short version

**Sound like a person communicating something, not a model producing output.**

Delete the sentence that only exists to introduce or summarize. Prefer concrete information over filler, hype, and vague language. When rewriting, preserve the author's **meaning, voice, and intent** — more formal is not automatically better.

The goal is writing that is **clear, specific, natural, and appropriate to its context**.

Full rationale and examples are in [`SKILL.md`](./SKILL.md).

## License

Apache License 2.0 — see [`LICENSE`](../LICENSE).
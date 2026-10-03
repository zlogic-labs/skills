---
name: skill-writer
description: "Create and refine executable Agent Skills from requirements, notes, workflows, postmortems, or existing SKILL.md files. Use when writing a new skill, converting operational knowledge into a skill, or reviewing a skill that is too long, vague, outdated, or dominated by debugging history."
---

# Skill Writer

Create Skills as **executable workflows**, not as documentation.

Transform source material into the smallest reliable set of instructions an Agent needs to complete a task correctly.

The process is:

1. Establish the Skill contract.
2. Collect the source material.
3. Extract the current workflow.
4. Write executable steps.
5. Mark confirmation points and hard constraints.
6. Compress the result.
7. Simulate execution.
8. Validate and report the result.

---

## 1. Establish the Skill Contract

Before writing content, determine:

* Skill directory
* `SKILL.md` location
* `name`
* `description`
* task the Skill handles
* expected completion state

Use:

```yaml
---
name: <skill-name>
description: "<what the skill does and when to use it>"
---
```

Requirements:

* `name` uses lowercase letters, numbers, and single hyphens.
* `name` matches the parent directory name.
* `name` does not start or end with `-` or contain consecutive hyphens.
* `name` is no longer than 64 characters.
* `description` is no longer than 1024 characters.
* `description` states both what the Skill does and when to use it.
* Do not add unnecessary frontmatter fields.
* Do not add a "When to use this skill" section to the body.

---

## 2. Collect the Source Material

Gather the information available for the task.

Use, in order of availability:

1. Existing Skill files
2. Project files and documentation
3. Scripts and tool usage
4. Established workflows
5. User requirements and notes
6. Other reliable project context

Inspect available project material before asking the user for information that may already exist.

If an essential fact cannot be determined reliably:

1. Identify exactly what is missing.
2. Check available files or tools.
3. Ask the user only if it still cannot be determined.

Never invent commands, paths, tool behavior, project conventions, or unsupported procedures.

---

## 3. Extract the Current Workflow

Reduce the source material to the actual execution flow before writing prose.

Extract:

* entry condition
* preparation
* ordered actions
* verification points
* user confirmation points
* failure conditions
* recovery actions
* completion condition

If multiple approaches exist, determine which one is currently supported.

If the supported approach cannot be determined reliably, ask instead of choosing silently.

---

## 4. Write Executable Steps

Write each important operation as a concrete step.

Use this structure:

```markdown
### N. <Action>

Do:
<command, tool call, or concrete operation>

Verify:
<specific success condition>

If this fails:
<specific recovery action, when needed>
```

Use real commands, paths, arguments, and ordering requirements when they are known.

For example:

````markdown
### 2. Install the required dependency

Do:

```bash
npx <tool> add <package>
```

Verify:

Confirm that the package appears in the project's dependency configuration.

If this fails:

1. Keep the existing project state unchanged.
2. Report the command output.
3. Do not substitute another package without determining that it is supported.

````

The example above demonstrates structure only. Do not copy its commands, package names, or assumptions into unrelated Skills.

Avoid vague instructions such as:

- "check the environment"
- "handle the issue"
- "make sure everything is correct"
- "use the appropriate tool"
- "fix it if necessary"

If a decision is required, define the condition and the resulting action.

---

## 5. Mark Confirmation Points and Constraints

### User confirmation

If the user must inspect, approve, provide input, or make a decision:

```text
Pause here and wait for user confirmation before continuing.
```

Do not assume confirmation.

### Invalid or destructive states

If a result must not be reused:

```text
Discard the current result and restart from step N.
```

### Hard constraints

Keep a constraint next to the step where it matters.

Use a separate `Rules` section only when a rule applies across the entire workflow and cannot naturally belong to one step.

Do not expose implementation details as rules unless they change the Agent's required behavior.

---

## 6. Compress the Skill

After writing the workflow, make three passes.

### Pass A: Remove history

Remove information about how the solution was discovered.

Keep only the resulting instruction.

> If a paragraph explains **how the team discovered the current solution** rather than **what the Agent should do now**, remove it or convert it into the resulting rule.

### Pass B: Remove non-executable information

Remove anything that does not change what the Agent should:

* do
* avoid
* verify
* stop for
* recover from

This normally removes background, implementation details, design rationale, historical measurements, and explanations already handled by tools.

### Pass C: Remove duplication

Each important rule should appear once, at the point where it is most useful.

Merge repeated explanations and move step-specific rules into their relevant steps.

After these passes, the Skill should contain the **minimum reliable execution procedure**, not a complete record of the source material.

---

## 7. Simulate Execution

Read the completed Skill as an Agent executing the task for the first time.

At every step, ask:

1. Where do I start?
2. What exactly do I do?
3. What should I verify?
4. Can I continue?
5. What do I do if it fails?
6. What does the next step require?
7. What proves the task is complete?

Fix every point where the Agent would need to guess:

* a command
* a parameter
* a path
* a supported approach
* whether a result is valid
* whether it can continue
* how to recover

Do not resolve missing information by inventing an answer. Return to the source material or ask the user.

---

## 8. Validate and Report

### Content validation

Confirm that:

* no debugging history remains
* no obsolete solution remains
* no vague operational instruction remains
* no unnecessary tool implementation detail remains
* no important rule is duplicated
* the workflow has a clear completion condition

### Size validation

Keep the main `SKILL.md` focused and reasonably small.

As a practical threshold, if the body approaches **500 lines or roughly 5,000 tokens**, look for material that should be moved out.

Split content only when it is genuinely needed but not needed for every execution.

Use supporting files such as:

```text
references/
scripts/
assets/
```

when appropriate.

The main `SKILL.md` should explain **when** supporting material is needed and **which file** to use. Do not move core workflow instructions into references merely to reduce line count.

### Final report

After creating or updating the Skill:

1. Report the file that was created or changed.
2. Briefly report the resulting structure or important changes.
3. Report unresolved information only if it prevented complete validation.

Do not report the editing process.

Do not reproduce removed debugging history unless the user explicitly asks for it.

---

## Core Principle

> **Write what the Agent must do now, not how someone eventually figured out what to do.**
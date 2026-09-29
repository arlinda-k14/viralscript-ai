# Skill Builder

Use this file to design, document, and register new skills for the AIOS.

## Skill Format

Each skill is a markdown file in `skills/` with the following sections:

```markdown
---
name: skill_name
description: One-line summary of what the skill does and when to use it.
---

# Title

## When to Use

## Instructions

## Examples
```

## Steps

1. Draft the skill in `skills/<skill_name>.md` using the format above.
2. Register it in `config/skills.json` so the loader can discover it.
3. Add relevant long-lived context to `memory/context.json`.

# AIOS

AI Operating System configuration and memory.

## Structure

```
.viralscript-ai/
  skills/      # Skill definitions (markdown)
  config/      # Loader configuration (JSON)
  memory/      # Persistent context (JSON)
```

## Usage

Skills are registered in `config/skills.json` and loaded from `skills/`.
See `skills/skill_builder.md` for the skill format.

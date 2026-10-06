# Skills Repository

This repo holds Claude skills, installable as a Claude Code plugin (via `.claude-plugin/marketplace.json`) or with skills.sh.

## Directory structure

```
skills/
└── skill-name/          # directory name = frontmatter `name`
    ├── SKILL.md         # required: entry point
    ├── references/      # optional: background knowledge Claude reads on demand
    ├── workflows/       # optional: one file per task
    └── templates/       # optional: output formats
```

- Directory and file names are `lowercase-with-hyphens`. The main file is exactly `SKILL.md`.
- No per-skill READMEs. Document each skill in the top-level README.md.

## SKILL.md frontmatter (required)

```yaml
---
name: skill-name
description: What it does and when to use it, including trigger phrases.
---
```

`name` must match the directory name. Claude uses `description` to decide when to load the skill, so make it specific.

## Writing skills

- Keep SKILL.md short; move long catalogs, frameworks, and step-by-step procedures into `references/` or `workflows/`.
- Link supporting files with relative markdown links, e.g. `[references/catalog.md](references/catalog.md)` — not backticks or plain paths.
- Write instructions Claude acts on, not explanations of concepts.

## Adding a skill

1. Create `skills/<skill-name>/SKILL.md`.
2. Add its path to the `skills` array in `.claude-plugin/marketplace.json`.
3. Add a row to the Available Skills table and a Skill Details section in README.md.

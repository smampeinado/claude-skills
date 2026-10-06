# claude-skills

A collection of [Claude skills](https://docs.claude.com/en/docs/agents-and-tools/agent-skills/overview), built mostly for Stanford GSB students, researchers, and faculty. Each skill lives in its own folder with a `SKILL.md` (the instructions Claude follows) and a `README.md` (what it does and how to install it).

## Skills

| Skill | What it does |
|---|---|
| [gsb-library-scout](gsb-library-scout/) | Tells you which licensed GSB Library databases (PitchBook, Capital IQ, Euromonitor, WRDS, and ~150 more) are most likely to answer your research question, what to pull from each, whether your Stanford role gives you access, and which license restrictions apply. |
| [person-background-research](person-background-research/) | Builds a short, sourced brief on a specific person — career, current focus, recent news, and conversation angles — tailored to why you're researching them (meeting prep, cold outreach, interview, investor pitch). Professional info only. |

## Install

**Claude (claude.ai / desktop app):** Settings → Capabilities → Skills → upload a skill's `SKILL.md` (or a zip of its folder).

**Claude Code:** copy a skill folder into `~/.claude/skills/`:
```bash
git clone https://github.com/<your-username>/claude-skills.git
cp -r claude-skills/gsb-library-scout ~/.claude/skills/
```

See each skill's README for details.

## Contributing

PRs welcome. To add a skill, create a new folder with a `SKILL.md` and `README.md`, then add a row to the table above.

---

Not affiliated with or endorsed by Stanford University or the Stanford GSB Library.

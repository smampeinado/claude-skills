# gsb-library-scout

A Claude skill for Stanford GSB students, researchers, and faculty. Ask Claude a research question ("What's the TAM for pet insurance in Brazil?", "Who's funding climate-fintech seed rounds?") and it tells you which **licensed GSB Library databases** are most likely to have the answer:

- Ranked resources, with what to pull from each (module, report, menu path)
- Whether **your role** (MBA/MSx, PhD, faculty, research staff, non-GSB Stanford, alum) gives you access
- License restrictions that apply: academic-use only, download caps, no scraping or AI extraction
- What the library *won't* answer, and the best public alternative

It covers about 150 resources from the GSB Library A–Z list: PitchBook, Capital IQ Pro, Preqin, AlphaSense, Euromonitor, IBISWorld, Gartner, WRDS, Redivis datasets, and more.

## Install

**Claude (claude.ai / desktop app):** Settings → Capabilities → Skills → upload `SKILL.md` (or a zip of this folder).

**Claude Code:**
```bash
mkdir -p ~/.claude/skills/gsb-library-scout
curl -o ~/.claude/skills/gsb-library-scout/SKILL.md \
  https://raw.githubusercontent.com/<your-username>/gsb-library-scout/main/SKILL.md
```

The first time it runs, Claude asks your role so it only recommends what you can access.

## Important

- **The skill points you to databases. It doesn't access them.** You still log in through the GSB Library links with Stanford SSO.
- **Respect the licenses.** Almost everything is academic use only: no internships, client work, or your own startup. PitchBook bans accounts that use AI tools or scrapers to collect data.
- **Holdings change every term.** This is a snapshot from October 2026. Check the [A–Z list](https://libguides.stanford.edu/az/databases) and [Collections Updates](https://libguides.stanford.edu/new) when it matters, and ask a librarian through [Ask Us](https://www.gsb.stanford.edu/library/research-support/ask-us) for anything tricky.
- This repo contains database names and publicly posted access notes only. It holds no licensed data.

## Contributing

PRs welcome when the library adds, renames, or cancels a resource. Please cite the Collections Updates post or A–Z entry in the PR description.

---

Not affiliated with or endorsed by Stanford University or the Stanford GSB Library.

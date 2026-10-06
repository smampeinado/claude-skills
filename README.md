# claude-skills

[Claude skills](https://docs.claude.com/en/docs/agents-and-tools/agent-skills/overview) for research, built mostly for Stanford GSB students, researchers, and faculty.

## Installation

**Claude Code (plugin):**
```bash
/plugin marketplace add smampeinado/claude-skills
/plugin install claude-skills@claude-skills
```

**Claude Code (skills.sh):**
```bash
npx skills add smampeinado/claude-skills
```

**Claude (claude.ai / desktop app):** Settings → Capabilities → Skills → upload a skill's `SKILL.md` (or a zip of its folder).

## Available Skills

| Skill | What It Does |
|-------|--------------|
| `gsb-library-scout` | Tells you which licensed GSB Library databases are most likely to answer your research question, what to pull from each, whether your Stanford role gives you access, and which license restrictions apply |
| `person-background-research` | Deep research on one person before cold outreach: rebuilt resume, career story, education (down to school mascots), everything they've written, interviews, and the personal details that could make them smile. Saves a sourced dossier |

## Skill Details

### GSB Library Scout

Ask a research question ("What's the TAM for pet insurance in Brazil?", "Who's funding climate-fintech seed rounds?") and get the licensed GSB Library resources most likely to have the answer:

- Ranked resources, with what to pull from each (module, report, menu path)
- Whether **your role** (MBA/MSx, PhD, faculty, research staff, non-GSB Stanford, alum) gives you access
- License restrictions that apply: academic-use only, download caps, no scraping or AI extraction
- What the library *won't* answer, and the best public alternative

Covers about 150 resources from the GSB Library A–Z list: PitchBook, Capital IQ Pro, Preqin, AlphaSense, Euromonitor, IBISWorld, Gartner, WRDS, Redivis datasets, and more. The first time it runs, Claude asks your role so it only recommends what you can access.

**Important:**
- **The skill points you to databases. It doesn't access them.** You still log in through the GSB Library links with Stanford SSO.
- **Respect the licenses.** Almost everything is academic use only: no internships, client work, or your own startup. PitchBook bans accounts that use AI tools or scrapers to collect data.
- **Holdings change every term.** This is a snapshot from October 2026. Check the [A–Z list](https://libguides.stanford.edu/az/databases) and [Collections Updates](https://libguides.stanford.edu/new) when it matters, and ask a librarian through [Ask Us](https://www.gsb.stanford.edu/library/research-support/ask-us) for anything tricky.
- The skill contains database names and publicly posted access notes only. It holds no licensed data.

**Trigger phrases:** research, market size, TAM, competitors, funding data, industry report, find data on, is there a dataset, GSB library, PitchBook, Capital IQ.

---

### Person Background Research

Deep research on an individual before you cold-email them. The goal is personal connection: finding the detail that makes them smile, like a CEO who started as a shop clerk or a journalist's first high school byline. It researches; it doesn't write the email.

Give Claude a name, something that tells them apart (company, school, or URL), and ideally their LinkedIn profile pasted or as a "Save to PDF" export. You get a dossier saved to `research/<name>.md` with:

- **Top 5 hooks** and an **avoid list** up front, plus the overused hook everyone else already uses
- **Resume** (theirs if public, otherwise rebuilt from LinkedIn), with what each company does
- **Career story:** fast rises, switches, humble starts, and why they made each move
- **Education** back to high school, with mascots and rivalries
- **Hometown, first job, and origin story**
- **Everything they've written,** including their first published piece, and how they write
- **Interviews** (podcasts, video, written Q&As) mined for anecdotes, numbers, and opinions
- **Personal life** (hobbies, teams, pets, causes), each tagged ✅ safe to mention or 👀 background only
- **Right now:** last 90 days of activity, role-specific focus, and recent news
- **Contact:** stated preferences and work email (found, or inferred and labeled unverified)

Works best with web search enabled. Pair with `connection-finder`, `fun-angle`, or `cold-email-coach` to write the email.

**Important:**
- **Self-shared details only.** Personal details are included only if the person shared them publicly, or (for public figures) they appeared in reputable press. No home addresses, personal contact info, kids' names, real-time location, people-search sites, data brokers, or paid lookup tools.
- **Knowing isn't the same as using.** Details tagged 👀 help you understand the person but would feel invasive in a cold email.
- **Verify before you rely on it.** Every claim is sourced and dated, but roles change and inferred emails can be wrong.

**Trigger phrases:** deep research on, dig into, background on, everything about, before I email, research this person, full dossier, who is.

## Repository Structure

```
claude-skills/
├── .claude-plugin/
│   └── marketplace.json
├── skills/
│   ├── gsb-library-scout/
│   │   └── SKILL.md
│   └── person-background-research/
│       ├── SKILL.md
│       ├── references/
│       │   ├── avoid-list.md
│       │   └── sources.md
│       └── templates/
│           └── dossier.md
├── CLAUDE.md
├── LICENSE
└── README.md
```

Skills can add `references/` (background knowledge), `workflows/` (one file per task), and `templates/` (output formats) folders as they grow.

## Contributing

PRs welcome. For `gsb-library-scout`, when the library adds, renames, or cancels a resource, cite the Collections Updates post or A–Z entry in the PR description. To add a skill, follow the conventions in [CLAUDE.md](CLAUDE.md).

## License

MIT License — See [LICENSE](LICENSE) for details.

---

Not affiliated with or endorsed by Stanford University or the Stanford GSB Library.

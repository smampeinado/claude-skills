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
| `person-background-research` | Builds a short, sourced brief on a specific person (career, current focus, recent news, conversation angles), tailored to why you're researching them |

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

Give Claude a name, something that tells the person apart from others with the same name (company, title, school, or a LinkedIn URL), and what the brief is for. You get back:

- A career snapshot and current role, with each fact linked and dated
- What they care about right now, drawn from their own posts, talks, and interviews
- Recent news
- 2–4 specific angles tailored to your purpose (meeting prep, cold outreach, interview, investor pitch, and more)
- Watch-outs, plus a list of what couldn't be verified

Works best with web search enabled.

**Important:**
- **Professional information only.** It won't collect home addresses, personal contact info, family details, or other private data, and it doesn't use people-search or data-broker sites.
- **Verify before you rely on it.** Every claim is sourced, but roles and titles change.
- At Stanford, it hands off to `gsb-library-scout` for licensed people databases (BoardEx, Capital IQ, PitchBook).

**Trigger phrases:** who is, look up, background on, research this person, prep me for my meeting with, what do I need to know about, dossier, bio.

## Repository Structure

```
claude-skills/
├── .claude-plugin/
│   └── marketplace.json
├── skills/
│   ├── gsb-library-scout/
│   │   └── SKILL.md
│   └── person-background-research/
│       └── SKILL.md
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

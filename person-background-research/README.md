# person-background-research

A Claude skill that builds a short, sourced background brief on a specific person before you meet, email, interview with, or pitch them.

Give Claude a name, something to tell them apart (company, title, school, or a LinkedIn URL), and what the brief is for. You get back:

- A career snapshot and current role, with each fact linked and dated
- What they care about right now, drawn from their own posts, talks, and interviews
- Recent news
- 2–4 specific angles tailored to your purpose (meeting prep, cold outreach, interview, investor pitch, and more)
- Watch-outs, plus a list of what couldn't be verified

## Install

**Claude (claude.ai / desktop app):** Settings → Capabilities → Skills → upload `SKILL.md` (or a zip of this folder).

**Claude Code:**
```bash
mkdir -p ~/.claude/skills/person-background-research
curl -o ~/.claude/skills/person-background-research/SKILL.md \
  https://raw.githubusercontent.com/<your-username>/claude-skills/main/person-background-research/SKILL.md
```

Works best with web search enabled.

## Important

- **Professional information only.** The skill covers someone's public professional life. It won't collect home addresses, personal contact info, family details, or other private data, and it doesn't use people-search or data-broker sites.
- **Verify before you rely on it.** Every claim is sourced, but roles and titles change. Check anything load-bearing.
- **Works with other skills.** At Stanford, it hands off to `gsb-library-scout` for licensed people databases (BoardEx, Capital IQ, PitchBook).

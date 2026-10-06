---
name: person-background-research
description: Builds a sourced, professional background brief on a specific individual — career history, current role, education, public work (writing, talks, podcasts, papers, companies, investments), stated interests, and recent news — tailored to why the user is researching them (meeting prep, cold outreach, interview, panel, networking, due diligence on a potential co-founder or investor). Use whenever the user names a person and wants to know who they are, what they've done, or how to approach them, even if they don't say "research." Triggers on "who is," "look up," "background on," "research this person," "prep me for my meeting with," "what do I need to know about," "dossier," "bio," "tell me about [name]."
---

# Person Background Research

The user names a person and wants to understand them. Produce a **short, sourced brief** about that person's **public professional life**, shaped around why the user cares. Every claim has a source. Anything you couldn't verify is labeled as such.

## Scope: what's in and out

**In:** professional history, current role and company, education, board seats, companies founded or backed, published writing, talks, podcasts, interviews, papers, patents, public social posts on professional topics, awards, press coverage, publicly stated views and interests.

**Out — don't collect or report, even if found:** home address, personal phone or email, family members (unless they're public figures in their own right or the person discusses them publicly in a professional context), health, religion, sexual orientation, finances beyond what's public in a professional role (e.g., SEC filings), criminal records of private individuals, and anything from leaked or breached data. If the user asks for these, decline briefly and offer the professional brief instead.

If the request looks like stalking, harassment, or locating someone who doesn't want to be found, stop and say why.

## Step 0: Get the two things you need

1. **Who, exactly.** Name plus at least one disambiguator: company, title, school, city, or a LinkedIn/URL. If the name is common and the user gave nothing else, ask one short question before searching.
2. **Why.** Purpose determines what matters. If not stated, ask once: *"What's this for — a meeting, cold outreach, an interview, or something else?"* If the user won't say, default to **meeting prep**.

| Purpose | Emphasize |
|---|---|
| Meeting / coffee chat prep | Current role and priorities, recent news, conversation openers, shared ground |
| Cold outreach | What they care about right now, what they've said publicly, hooks for a specific ask |
| Job interview (they're the interviewer) | Their career path, team/org, what they've said about hiring and culture |
| Panel / speaker intro | Accurate bio, signature accomplishments, correct title and pronunciation if findable |
| Potential investor | Fund, thesis, check size, stage, portfolio overlaps and conflicts, public takes |
| Potential co-founder / hire / partner | Track record, prior companies and outcomes, references in public record, red flags |

## Workflow

1. **Lock identity.** Find the canonical profile (LinkedIn, company bio page, personal site, faculty page). Confirm it's the right person by matching at least two disambiguators. If there are multiple plausible matches, say so and list them — never blend two people into one profile.
2. **Search in layers**, stopping when you have enough for the purpose:
   - **Primary/self-authored:** LinkedIn, personal site, company or faculty bio, Substack/blog, X/Bluesky/Threads, GitHub, Google Scholar.
   - **Their voice:** podcast appearances, conference talks (YouTube), interviews, op-eds, books. These are the best source of what they actually care about.
   - **Third-party:** news coverage (last 24 months first), Crunchbase/PitchBook-style profiles, SEC filings (Form 4, proxy statements) for public-company executives and directors, press releases.
   - **Stanford-specific (if the user is at Stanford):** GSB/Stanford news, faculty profiles, alumni features. For licensed people databases (BoardEx, Capital IQ people search, PitchBook investor profiles), hand off to the `gsb-library-scout` skill rather than guessing what's licensed.
3. **Date everything.** Roles change. Note when each key fact was last confirmed (e.g., "per LinkedIn, as of Oct 2026"). Flag anything older than ~12 months that could be stale.
4. **Find the angle.** Pull 2–4 specific, non-obvious hooks tied to the purpose — a podcast quote, a recent post, an unusual career move, a cause they champion. Generic hooks ("you both like tech") don't count. If the user has shared their own background, note genuine overlaps; for deeper overlap-finding, the `connection-finder` skill fits.
5. **Self-check before output.** Every factual claim has a link. No claim comes from a source about a different person with the same name. Unverified items are marked.

## Output format

No preamble. Keep the whole brief under ~400 words unless the user asks for more.

```
## [Full Name] — [Current Title], [Organization]
*Researched for: [purpose] · Confidence in identity: High / Medium / Low*

**In one line:** [who they are and why they matter to this purpose]

**Career snapshot**
- [Current role, since YYYY] — [source]
- [Prior role(s), most relevant first] — [source]
- [Education] — [source]

**What they care about right now**
- [Theme + evidence: quote, post, talk, with date] — [source]

**Recent news (last 12–24 months)**
- [Date] [Item] — [source]

**Angles for [purpose]**
1. [Specific hook and how to use it]
2. ...

**Watch-outs**
- [Sensitive topics, recent controversy, conflicts, things not to bring up, stale info]

**Couldn't verify**
- [Claims found but not confirmed, or gaps]
```

## Rules

- **Cite or cut.** No source, no claim. Prefer the person's own words and primary sources over aggregators.
- **Never invent.** Don't guess titles, dates, alma maters, or quotes. "Not found" is a valid answer.
- **Quote sparingly.** Short quotes only, with attribution; summarize everything else.
- **Don't overreach in tone.** The brief is for the user's preparation. Remind the user, when relevant, not to open an email or meeting by reciting someone's history back to them — use one well-chosen hook.
- **Respect platform rules.** Don't scrape, don't log in to anything on the user's behalf, and don't use people-search / data-broker sites.

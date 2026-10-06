---
name: person-background-research
description: Deep research on one individual before cold outreach — rebuilds their resume from LinkedIn (pasted or PDF) with what each company does, reads the story of their career path, digs into education (down to high school and school mascots), catalogs everything they've written and every interview they've given, and mines it all for personal details that could make them smile (hometown, hobbies, pets, first job, first byline). Flags topics to avoid and the hook everyone else already uses. Saves a sourced dossier to research/<name>.md. Research only — does not draft the email. Use whenever the user is about to cold-email, DM, or pitch a specific person and wants to know everything about them first. Triggers on "deep research on," "dig into," "background on," "everything about," "before I email," "research this person," "full dossier," "who is."
---

# Person Background Research

The user is about to cold-email someone and wants to know as much as possible about them first. The goal is **personal connection**: finding the detail that makes the recipient smile ("you started as a shop clerk at Kroger?", "your first byline was in the Lakeside High *Spartan*"), not mastering their technical work.

You do the research. You **don't** write the email, subject lines, or opening lines. Hand off to `connection-finder` (overlaps with the user's background), `fun-angle`, or `cold-email-coach` for that.

## Privacy rule

**Include a personal detail only if the person shared it publicly themselves** (their own posts, writing, interviews, bio, personal site) **or, for public figures, it appeared in reputable press or Wikipedia.**

- ✅ OK: "Said on a 2024 podcast they have three kids." "Lives in the Bay Area." "Surfs in Baja most summers (own Instagram caption, public)."
- ❌ Never collect: home address, personal phone or email, kids' names or schools, real-time or recent location, anything inferred from photo metadata or backgrounds, people-search or data-broker sites, leaked data, paid lookup tools (RocketReach, Apollo, etc.) unless the user explicitly authorizes them for that search.
- City/region-level location only.

Tag every personal detail in the dossier:
- **✅ safe to mention** — fine to reference in a cold email.
- **👀 background only** — helps the user understand the person, but referencing it would feel like surveillance (family, vacations, where they live, anything from years-old personal posts).

If the request looks like stalking, harassment, or locating someone, stop and say why.

## Step 0: Inputs

Ask in one message for anything missing:

1. **Who:** full name + one disambiguator (company, title, school, city, or URL).
2. **LinkedIn:** "Can you paste their LinkedIn profile or upload the 'Save to PDF' export? I can't see most of LinkedIn without logging in." If the user can't, proceed with public sources and note the resume may be incomplete.
3. **Their resume,** if the user has one.

Then scale effort to footprint:
- **Public figure** (Wikipedia page, frequent press): full depth, read Wikipedia first.
- **Semi-private** (LinkedIn, a few posts or talks): full workflow, expect thinner sections.
- **Thin profile** (almost nothing public): say so plainly, don't pad, and suggest a warm intro (`warm-intro-finder`).

## Workflow

Lock identity first: match at least two disambiguators before using any source. If multiple people share the name, list them and ask. Never blend two people.

Then research each section. Where to look for each is in [references/sources.md](references/sources.md); what to flag or avoid is in [references/avoid-list.md](references/avoid-list.md).

1. **Resume.** Use their actual resume if public (personal site, speaker kit, old PDF). Otherwise rebuild it from LinkedIn. For each role: title, dates, and a one-line description of what the company does, its size or stage when they joined, and anything notable (acquired, IPO'd, shut down).
2. **Career story.** What's notable about the path: unusually fast promotions, career switches, long tenure, a step down to go somewhere interesting, a humble start, boomerang returns. Include **why** they left or joined each role, in their own words where you can find them.
3. **Education.** Every school, degree, and year, back to high school when findable. Include the **mascot** for each school and any famous **rivalries**. Note clubs, teams, school papers, or honors they mention.
4. **Hometown and origin.** Where they grew up, moves, immigration story, first job (especially humble or surprising ones).
5. **Writing.** Catalog everything: books, papers, articles, op-eds, blog/Substack posts, notable social threads. Find their **first published piece**. Read in full: the first piece, the most personal pieces, and the ~10 most recent. Skim the rest only for personal details. Note **how they write** (formal/casual, long/short, emoji, humor) so the user can match it.
6. **Interviews.** Podcasts, video, written Q&As, profiles. These are the richest source of personal details; prioritize long-form (45+ min) ones. Capture specific anecdotes (year, place, names), **numbers they cite** about their work, and **contrarian opinions**.
7. **Personal life (within the privacy rule).** Hobbies, sports teams, pets, causes, boards and nonprofits, family (only as self-disclosed, e.g. "has three kids"), city/region they live in, places they love to travel. Look for small joyful things: a running joke, a quirky hobby, a dog with an Instagram.
8. **Who helped them.** Mentors they credit, stories of a cold email or lucky break that changed their life.
9. **Right now.**
   - Their last 90 days of posts and talks: what's on their mind.
   - Role-specific focus — **journalist:** their last 5 stories and what they're covering now; **VC:** fund, stated investment focus, recent deals; **CEO/exec:** recent company moves, launches, hiring; **hiring manager:** open roles on their team, posts about culture or hiring.
   - News: last **30 days** on the person, last **90 days** on their company.
10. **Overused hooks.** What everyone already emails them about (the famous exit, the viral post, the obvious school tie). Name it so the user doesn't send the 500th version.
11. **Contact.**
    - Any stated preferences ("how to pitch me," "I don't read cold DMs," preferred channel).
    - **Work email:** look for it publicly (personal site, author bios, press releases, papers, GitHub commits on public work repos). If not found, infer the company's email pattern from other public employee addresses and label it **inferred, unverified**. Never personal email.
12. **Avoid list.** Run the dossier against [references/avoid-list.md](references/avoid-list.md) and flag what to stay away from and why.

## Output

Fill [templates/dossier.md](templates/dossier.md) and save it to `research/<firstname-lastname>.md` in the current working directory (create `research/` if needed). If the file already exists, update it in place and note what changed at the top. In chat, reply with only the **Top 5 hooks**, the **avoid list**, and the file path.

## Rules

- **Cite or cut.** Every claim gets a link and, for anything that can go stale, a date.
- **Never invent.** Don't guess mascots, dates, quotes, or emails. "Not found" is a valid answer.
- **Their own words beat summaries.** Prefer primary sources over aggregators.
- **Short quotes only,** attributed; summarize everything else.
- **Don't scrape or log in** to anything on the user's behalf.

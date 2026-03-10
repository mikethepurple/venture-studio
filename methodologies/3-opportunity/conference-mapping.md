<!-- scope: per-market -->

# Conference Mapping

## When to use

Always runs in step 3. Finds industry conferences for this market and maps the ecosystem through their partner, sponsor, and media pages. Produces an ecosystem map, not a competitor list.

## Inputs needed

- brief.md
- step-2/decisions.md

## Process

1. **Find relevant conferences.** Search for:
   - "[industry] conference [current year]"
   - "[topic] summit"
   - "[audience] expo"
   - Look for both large industry events and niche/focused conferences
   - Target 5-10 conferences

2. **Scrape each conference's ecosystem pages:**
   - **Sponsors:** Who is paying to be visible at these events? Sponsors = companies with budget in this space. Note sponsor tiers (platinum/gold/silver — tier reveals spend level).
   - **Partners:** Who are the official partners? These are ecosystem players with strategic interest.
   - **Media partners:** Which publications cover this space? These are the channels to reach the audience.
   - **Speakers:** Who are the thought leaders? Look for company affiliations, not just names.
   - **Exhibitors:** Who is selling to this audience? Exhibitor lists are gold for mapping vendors.

3. **Map the ecosystem.** From the conference data, categorize:
   - **Key players:** Companies appearing across multiple conferences
   - **Media outlets:** Publications and podcasts covering this space
   - **Communities:** User groups, meetups, and online communities mentioned
   - **Influencers:** Speakers who appear at multiple events or have large followings

4. **This is an ecosystem map, not a competitor list.** Competitor-mapping handles direct competitors. This agent maps the broader landscape: who has attention, money, and influence in this space.

## Output format

```markdown
# Conference Mapping — [Market Name]

*Date: [today]*

## Conferences Found

| Conference | Date | Location | Attendees | URL |
|---|---|---|---|---|
| [name] | [date] | [city/virtual] | [X] | [url] |

## Sponsors & Partners

| Company | Appears At | Role | Tier |
|---|---|---|---|
| [name] | [conference 1, conference 2] | Sponsor / Partner / Exhibitor | [platinum/gold/silver] |

## Media Outlets

| Outlet | Type | Reach | Conferences |
|---|---|---|---|
| [name] | Blog / Podcast / Newsletter / Magazine | [subscribers/readers] | [which conferences] |

## Key Ecosystem Players

[Companies appearing across 2+ conferences — these have strategic interest in the space]
- **[Company]** — [what they do, why they're relevant]

## Influencers & Thought Leaders

| Name | Company | Role | Conferences | Reach |
|---|---|---|---|---|
| [name] | [company] | [title] | [which events] | [followers/subscribers] |

## Ecosystem Summary

[2-3 sentences: who controls attention and money in this space, what the power structure looks like, where a new entrant could find leverage]

## Sources Used

- [URL — must match a citation above]
```

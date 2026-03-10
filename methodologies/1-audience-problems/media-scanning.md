# Media Scanning

## When to use

Always runs in step 1 (wave 2). Searches niche media for problem-focused content — "how to" articles, listicles, and clickbait that signals what problems the audience cares about.

## Inputs needed

- brief.md
- community-mapping.md

## Process

1. **Identify niche media sources** for this audience. Search for:
   - Industry blogs and publications
   - YouTube channels with tutorials
   - Popular newsletter/Substack writers
   - Podcast topics
   - Use community-mapping.md to find media sources mentioned or linked in communities

2. **Search for problem-focused content.** Look for articles with these patterns:
   - "How to [solve problem]" — if media publishes how-to content, the problem gets clicks
   - "X ways to fix [problem]" — listicles signal widespread interest
   - "[Problem] is killing your [outcome]" — fear/pain headlines
   - "Why [current solution] doesn't work" — dissatisfaction content
   - "I switched from [X] to [Y]" — switching stories reveal pain with incumbents

3. **Extract problems from content.** For each piece of content:
   - What problem does this article address?
   - How many views/shares/comments? (engagement = audience resonance)
   - Is this a one-off article or part of a recurring theme?

4. **Tag evidence as `[secondary]`** — media content is synthesized, not firsthand experience.

5. **Don't deduplicate or score.** Raw extraction only.

## Output format

```markdown
# Media Scanning — [Audience]

*Date: [today]*

## Media Sources Found

| Source | Type | Audience Size |
|---|---|---|
| [name] | Blog / YouTube / Newsletter / Podcast | [subscribers/followers] |

## Problems Found

### M-01: [Problem implied by the content]
**Content:** "[article title]" — [source/URL]
**Evidence:**
- `[secondary]` [summary of what the article addresses] — [URL] ([views/shares/comments])
**Recurring theme?** [yes — X similar articles found / no — one-off]

### M-02: [Problem]
**Content:** "[title]" — [URL]
**Evidence:**
- `[secondary]` [summary] — [URL] ([engagement])
**Recurring theme?** [assessment]

[Continue for all problems found]

## Sources Used

- [URL — must match a citation above]
```

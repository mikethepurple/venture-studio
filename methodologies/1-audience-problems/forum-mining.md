# Forum Mining

## When to use

Always runs in step 1 (wave 2). Searches forums and Reddit communities from the community map for complaints, frustrations, and recurring questions. Extracts raw problems with evidence.

## Inputs needed

- brief.md
- community-mapping.md

## Process

1. **Read community-mapping.md** and identify all Reddit and forum communities listed.

2. **For each community, search for pain language.** Search within each community for:
   - Complaints and frustrations ("hate," "annoying," "frustrated," "wish," "sick of")
   - Recurring questions that signal confusion or unmet needs ("how do I," "is there a way to," "anyone know")
   - Rants and vents about the topic area
   - Requests for help or recommendations

3. **Extract raw problems.** For each distinct problem found:
   - Write the problem in the audience's own language (not jargon)
   - Include 1-3 direct quotes with source URLs
   - Note engagement signals: upvotes, replies, likes
   - Tag evidence as `[primary]` (firsthand account) or `[secondary]` (synthesized claim)

4. **Don't deduplicate, score, or rank.** If the same problem appears in 3 communities, list it 3 times with all evidence. Dedup happens downstream.

5. **Don't mine reviews or media.** Those are separate agents. Only search forums and Reddit.

## Output format

```markdown
# Forum Mining — [Audience]

*Date: [today]*

## Problems Found

### F-01: [Problem statement in audience's words]
**Evidence:**
- `[primary]` "[quote]" — [source/URL] ([X] upvotes, [Y] replies)
- `[primary]` "[quote]" — [source/URL] ([engagement])
**Community:** [which community from the map]

### F-02: [Problem statement]
**Evidence:**
- `[primary]` "[quote]" — [source/URL] ([engagement])
**Community:** [community]

[Continue for all problems found — aim for 10-20 raw entries]

## Communities Searched

| Community | Posts Reviewed | Problems Found |
|---|---|---|
| [name] | [~X posts] | [X problems] |

## Sources Used

- [URL — must match a citation above]
```

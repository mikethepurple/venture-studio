# Review Mining

## When to use

Always runs in step 1 (wave 2). Finds tools and services the audience uses and mines their reviews for complaints and unmet needs. Focuses on 1-star and 3-star reviews.

## Inputs needed

- brief.md
- community-mapping.md

## Process

1. **Identify tools and services the audience uses.** Based on brief.md and the communities mapped, search for:
   - SaaS products serving this audience
   - Mobile apps they use
   - Physical products or services
   - Freelancers/agencies they hire

2. **Find reviews on major platforms:**
   - G2 and Capterra (B2B software)
   - Trustpilot (services)
   - App Store and Google Play (mobile apps)
   - Amazon (physical products)
   - Google Business reviews (local services)
   - Product Hunt (tech products)

3. **Mine 1-star reviews** — these reveal unmet needs, broken promises, dealbreakers. Extract the core complaint.

4. **Mine 3-star reviews** — these reveal "good enough but..." pain. The product works but something specific is frustrating. These are often better problem signals than 1-star reviews.

5. **Extract raw problems.** For each distinct problem:
   - Problem statement in the reviewer's words
   - 1-3 direct quotes with source URLs
   - Which product/service the review is about
   - Star rating
   - Tag all evidence as `[primary]`

6. **Don't deduplicate, score, or rank.** Raw extraction only.

## Output format

```markdown
# Review Mining — [Audience]

*Date: [today]*

## Products Reviewed

| Product | Platform | Review Count | Avg Rating |
|---|---|---|---|
| [name] | G2 / Trustpilot / etc. | [X reviews] | [X.X stars] |

## Problems Found

### R-01: [Problem statement in reviewer's words]
**Product:** [name]
**Evidence:**
- `[primary]` "[quote]" — [source/URL] ([star rating])
- `[primary]` "[quote]" — [source/URL] ([star rating])

### R-02: [Problem statement]
**Product:** [name]
**Evidence:**
- `[primary]` "[quote]" — [source/URL] ([star rating])

[Continue for all problems found]

## Sources Used

- [URL — must match a citation above]
```

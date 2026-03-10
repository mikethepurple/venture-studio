# Reddit Seeding

## When to use

Runs in step 6 execution. Creates an organic Reddit distribution plan for audiences active on specific subreddits. Best for developer tools, productivity tools, and niche B2B.

## Inputs needed

- brief.md
- step-4/decisions.md (product description, value prop)
- Any landing page or product URL from the current iteration's build output

## Process

1. **Subreddit research:** For each candidate subreddit:
   - Check subscriber count (>10K is meaningful)
   - Read top 10 posts of all time (what gets upvoted?)
   - Read sidebar rules (what's allowed? self-promotion rules?)
   - Look for existing posts about the problem (engagement, sentiment)
   - Score: High / Medium / Low fit

2. **Draft 3 post variations:**

   **Type A — "Show HN" style:**
   "I built X because I kept running into Y — would love feedback"
   Problem (personal, relatable) → what I tried → what I built → honest ask.

   **Type B — Question / community intel:**
   "How are you handling [problem]?" + context about what you're building.
   Genuine question + soft awareness.

   **Type C — Value post (if you have data/insight):**
   "[Insight] about [domain] — something I noticed while building in this space"
   The insight first, product mention second.

3. **Engagement plan:**
   - Post Tuesday-Thursday, 8-10am ET
   - Respond to every comment within 2 hours
   - Never delete negative comments — engage honestly
   - Follow up 1 week later with an update

4. **Cross-posting strategy:** Start in smaller subs to refine, then go to larger ones.

## Output format

```markdown
# Reddit Plan — [Product Name]

## Subreddit Analysis
| Subreddit | Subscribers | Fit | Self-promo rules | Notes |
|---|---|---|---|---|

## Post Drafts
### Post A: [title]
[full body]
**Target sub:** [name]

### Post B: [title]
[full body]
**Target sub:** [name]

### Post C: [title]
[full body]
**Target sub:** [name]

## Posting Schedule
| Date | Sub | Post type | Notes |
|---|---|---|---|

## Engagement Guidelines
[rules for responding]
```

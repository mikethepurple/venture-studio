# Facebook / Instagram Ads

## When to use

Runs in step 6 execution. Produces a complete Meta ad campaign brief for validation. Best for B2C, consumer-adjacent B2B, and audiences describable with interest + demographic targeting.

## Inputs needed

- brief.md
- step-4/decisions.md (business model, value prop)
- step-5/*.md (success criteria)
- Any landing page or product URL from the current iteration's build output

## Process

1. **Build audience targeting spec:**
   - 5-10 specific interests (tools, publications, competitors the audience follows)
   - Behavioral signals (business owners, online shoppers, tech early adopters)
   - Demographics (age, geography, income if premium)
   - Recommend budget split: 60% interest targeting, 40% broad

2. **Write 3 ad variations** (each tests a different angle):

   **Variation A — Pain-led:**
   Hook = the specific frustration. Body = why alternatives fail + your solution. CTA.

   **Variation B — Outcome-led:**
   Hook = the result they want. Body = how you deliver it. CTA.

   **Variation C — Social proof / curiosity:**
   Hook = "[X] people have already..." or a surprising insight. Body = the story. CTA.

   For each: primary text (125 chars), headline (40 chars), description (30 chars), image/video description.

3. **Campaign structure:**
   ```
   Campaign: [Product] Validation
     Ad Set 1: Interest — [primary audience]
       All 3 variations
     Ad Set 2: Broad (if budget >$50/day)
       Top 2 after 3 days
   ```

4. **Setup checklist:**
   - Meta Pixel installed and firing
   - Conversion event configured
   - UTM parameters on all links
   - Budget: $20-30/day per ad set
   - Review after 72 hours, pause underperformers

5. **Performance benchmarks:**
   | Metric | Pause | Good | Strong |
   |---|---|---|---|
   | CTR | <0.5% | 1-2% | >3% |
   | CPC | >$5 | $1-3 | <$1 |
   | CPL | >$20 | $5-10 | <$5 |

## Output format

```markdown
# Facebook Ads Brief — [Product Name]

## Audience Targeting
[targeting spec]

## Ad Variations
### A: Pain-led
[copy]
### B: Outcome-led
[copy]
### C: Social proof
[copy]

## Campaign Structure
[structure]

## Setup Checklist
[checklist]

## Expected Performance
[benchmarks and budget recommendation]
```

# Counter-Evidence

<!-- model: haiku -->

## When to use

Always runs in step 4 (wave 2). Actively searches for real-world failures, contradicting data, and market skepticism that challenge the revenue model and GTM strategy. Does not remove or invalidate — just finds counter-evidence.

## Inputs needed

- brief.md
- step-3/decisions.md
- revenue-model.md
- gtm-strategy.md
- pricing-research.md

## Process

1. **Read revenue-model.md, gtm-strategy.md, and pricing-research.md.** Extract the 5-8 most critical claims and assumptions that drive the business model. Examples:
   - Revenue projections assume X% conversion rate
   - CAC assumption of $X via Telegram
   - Market will reach $X by Year 3
   - Users willing to pay $X/month
   - Growth loop via viral sharing will achieve X coefficient

2. **For EVERY critical assumption, search for counter-evidence.** Flip the framing:
   - If claim is "prediction markets growing rapidly" → search "prediction market declining," "prediction market hype," "prediction market failed"
   - If claim is "Telegram Mini Apps drive viral growth" → search "Telegram Mini App retention problems," "Telegram Mini App failed," "mini app low engagement"
   - If claim is "USDT adoption growing in CIS" → search "crypto ban Russia," "USDT regulation CIS," "crypto adoption declining"
   - If claim is "$X CAC via crypto channels" → search "crypto user acquisition expensive," "crypto CAC rising," "Telegram ads ineffective"

3. **Search for failed prediction market / betting startups.**
   - Search: "prediction market startup failed," "betting startup shutdown," "Probo India banned," "prediction market regulatory crackdown"
   - Search: "crypto betting closed," "Telegram trading bot scam," "mini app abandoned"
   - Document: what they built, why they failed, how their model compares to this solution

4. **Search for CIS market skepticism.**
   - Search: "Russia crypto regulation risk," "CIS fintech challenges," "emerging market payment problems"
   - Search: "Telegram mini app problems," "TON ecosystem criticism," "USDT risk"
   - Look for analyst reports or VC blog posts expressing skepticism

5. **Record findings.** For each assumption:
   - Counter-evidence found (with URLs and sources)
   - Counter-evidence NOT found (searched but nothing contradicted)
   - Quality of counter-evidence (strong rebuttal vs weak/irrelevant)
   - Assign confidence score /5 (5 = no meaningful counter-evidence, 1 = strong contradiction)

## Output format

```markdown
# Counter-Evidence — [Solution Name]

*Date: [today]*

## Assumptions Tested

### A-01: [Assumption statement]
**Source:** [revenue-model.md / gtm-strategy.md / pricing-research.md]
**Claim:** [exact claim being tested]

**Counter-evidence found:**
- [evidence + source/URL] — strength: [strong/moderate/weak]
- [evidence + source/URL] — strength: [strength]

**Counter-evidence NOT found:**
- Searched for: "[search query]" — no contradicting results

**Confidence:** [X]/5 — [one-line rationale]

### A-02: [Assumption statement]
[same structure]

[Continue for ALL assumptions — minimum 5, do not skip any]

## Failed Startups / Cautionary Tales

| Company | What They Built | Why They Failed | Relevance to This Solution |
|---|---|---|---|
| [name] | [1-line description] | [reason] | [how it applies] |

## Market Skepticism

| Skeptic Claim | Source | Strength | Relevance |
|---|---|---|---|
| [claim] | [URL] | [strong/moderate/weak] | [how it applies] |

## Summary

| Assumption | Confidence /5 | Key Counter-Evidence | Impact |
|---|---|---|---|
| A-01 | [X] | [one-line or "none found"] | [undermines/weakens/irrelevant/none] |
| A-02 | [X] | [one-line] | [impact] |

**Overall model confidence:** [X]/5 — [one-sentence assessment]

## Sources Used

- [URL — must match a citation above]
```

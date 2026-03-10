# Counter-Evidence

## When to use

Always runs in step 1 (wave 5). Actively searches for contradicting evidence for every problem's key claims. Assigns a confidence score to each problem's evidence base. Does not remove or invalidate anything.

## Inputs needed

- brief.md
- prevalence-check.md
- wtp-signals.md

## Process

1. **Read prevalence-check.md and wtp-signals.md.** For each problem, identify the 1-2 key claims that drive its prevalence and WTP scores.

2. **For EVERY problem, search for counter-evidence.** Flip the framing in search queries:
   - If claim is "80% of [audience] struggle with X" → search "X solved," "[audience] satisfied with X," "X not a problem"
   - If claim is "people pay $50/mo for workarounds" → search "free alternatives to X," "X not worth paying for," "[tool] free tier sufficient"
   - If claim is "growing demand" → search "[topic] declining interest," "[topic] oversaturated," "[topic] hype cycle"

3. **Record what you find.** For each problem:
   - Counter-evidence found (with URLs and sources)
   - Counter-evidence NOT found (you searched but nothing contradicted the claim)
   - Quality of counter-evidence (strong rebuttal vs weak/irrelevant)

4. **Assign a confidence score /5** to each problem's overall evidence base:
   - 5 = no meaningful counter-evidence found, claims well-supported from multiple angles
   - 4 = minor counter-evidence exists but doesn't undermine the core claim
   - 3 = some counter-evidence weakens the claim, mixed picture
   - 2 = significant counter-evidence, core claim is shaky
   - 1 = strong counter-evidence directly contradicts the key claims

5. **Don't remove or invalidate problems.** Don't change scores. Just find counter-evidence and assign confidence. The ranking agent will weight by confidence.

## Output format

```markdown
# Counter-Evidence — [Audience]

*Date: [today]*

## Counter-Evidence by Problem

### P-01: [Problem name]
**Key claims tested:**
1. [claim from prevalence or WTP]
2. [claim]

**Counter-evidence found:**
- [evidence + source/URL] — strength: [strong/moderate/weak]

**Counter-evidence NOT found:**
- Searched for: "[search query]" — no contradicting results

**Confidence:** [X]/5 — [one-line rationale]

### P-02: [Problem name]
[same structure]

[Continue for ALL problems — do not skip any]

## Summary

| Problem | Confidence /5 | Key Counter-Evidence | Impact on Claim |
|---|---|---|---|
| P-01 | [X] | [one-line or "none found"] | [undermines / weakens / irrelevant / none] |
| P-02 | [X] | [one-line] | [impact] |

## Sources Used

- [URL — must match a citation above]
```

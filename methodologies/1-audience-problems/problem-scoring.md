# Problem Scoring
<!-- model: sonnet -->


## When to use

Always runs in step 1 (wave 4). Scores each problem on severity, frequency, and underserved dimensions. These are judgment calls based on the dedup descriptions — no web research needed.

## Inputs needed

- brief.md
- problem-dedup.md

## Process

1. **Read problem-dedup.md** and review all problems (P-01, P-02, etc.) with their evidence.

2. **Score each problem on three dimensions based on the evidence already gathered:**

   **Severity (/5):** How painful is this problem?
   - 5 = people lose significant money or time daily, emotional distress
   - 4 = meaningful disruption to workflow or life
   - 3 = noticeable inconvenience
   - 2 = minor annoyance
   - 1 = barely registers

   **Frequency (/5):** How often does the audience encounter this?
   - 5 = daily or multiple times per day
   - 4 = several times per week
   - 3 = weekly
   - 2 = monthly
   - 1 = a few times a year or less

   **Underserved (/5):** How well do existing solutions address this?
   - 5 = no good solution exists, people suffer or build DIY workarounds
   - 4 = solutions exist but are expensive, clunky, or incomplete
   - 3 = decent solutions exist but significant gaps remain
   - 2 = good solutions exist, minor gaps
   - 1 = well-served by multiple quality products

3. **Base scores on evidence, not speculation.** If the dedup list shows lots of DIY workarounds, underserved is high. If evidence mentions daily frustration, frequency is high. If evidence is thin, score conservatively.

4. **Don't research anything.** Don't search the web. Score purely from what's in problem-dedup.md.

5. **Don't score prevalence or WTP.** Those are separate agents with web research.

## Output format

```markdown
# Problem Scoring — [Audience]

*Date: [today]*

## Scores

| Problem | Severity /5 | Frequency /5 | Underserved /5 | Rationale |
|---|---|---|---|---|
| P-01: [name] | [X] | [X] | [X] | [1-2 sentences justifying scores based on evidence] |
| P-02: [name] | [X] | [X] | [X] | [rationale] |

[Continue for all problems]

## Scoring Notes

- Highest severity: P-[X] — [why]
- Highest frequency: P-[X] — [why]
- Most underserved: P-[X] — [why]
```

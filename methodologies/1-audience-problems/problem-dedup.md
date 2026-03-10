# Problem Dedup
<!-- model: sonnet -->


## When to use

Always runs in step 1 (wave 3). Merges all wave-2 outputs into one deduplicated problem list. Combines overlapping problems and tags each with source type. Does not score.

## Inputs needed

- brief.md
- forum-mining.md
- review-mining.md
- media-scanning.md
- workaround-detection.md

## Process

1. **Collect all raw problems** from the four wave-2 agents: forum-mining, review-mining, media-scanning, workaround-detection.

2. **Identify overlaps.** Two problems overlap if they describe the same underlying pain, even if worded differently. Problems are NOT overlapping just because they're in the same topic area — "can't find reliable suppliers" and "suppliers ghost after first order" are different problems.

3. **Merge overlapping problems.** When problems overlap:
   - Combine into one entry with the clearest problem statement
   - Preserve ALL evidence from both entries
   - Note which originals were merged

4. **Tag each problem with source types:**
   - `[forum]` — from forum-mining.md
   - `[review]` — from review-mining.md
   - `[media]` — from media-scanning.md
   - `[workaround]` — from workaround-detection.md
   - Problems with 3-4 source types are stronger signals than single-source problems

5. **Assign an ID** to each unique problem (P-01, P-02, etc.) for reference by downstream agents.

6. **Don't score, rank, or filter.** Just deduplicate and tag.

## Output format

```markdown
# Problem Dedup — [Audience]

*Date: [today]*

## Deduplicated Problems

### P-01: [Problem statement]
**Source types:** `[forum]` `[review]` `[workaround]`
**Evidence count:** [X] pieces across [Y] sources
**Key evidence:**
- [strongest quote or data point with source]
- [second strongest]
**Merged from:** forum-mining F-03, review-mining R-07, workaround-detection W-02

### P-02: [Problem statement]
**Source types:** `[forum]`
**Evidence count:** [X] pieces
**Key evidence:**
- [evidence with source]
**Merged from:** forum-mining F-01

[Continue for all unique problems]

## Merge Log

| Merged Into | Original Entries | Reason |
|---|---|---|
| P-01 | F-03, R-07, W-02 | [why these are the same problem] |

## Stats

- Raw problems input: [X] (forum) + [X] (review) + [X] (media) + [X] (workaround)
- After dedup: [X] unique problems
- Multi-source problems: [X] (appearing in 2+ source types)
- Single-source problems: [X]
```

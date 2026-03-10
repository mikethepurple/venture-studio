# Idea Dedup
<!-- model: sonnet -->


## When to use

Always runs in step 2 (wave 2). Merges all wave-1 idea outputs into one deduplicated list. Combines overlapping concepts. Does not score or evaluate.

## Inputs needed

- brief.md
- seed.md
- idea-volume.md
- idea-tech.md
- prior-art.md

## Process

1. **Collect all concepts** from idea-volume.md, idea-tech.md, and any novel approaches observed in prior-art.md.

2. **Identify overlaps.** Two concepts overlap if they solve the same problem for the same user in essentially the same way, even if worded differently. Different business models or delivery methods for the same core idea are NOT overlaps — keep them separate.

3. **Protect seed concepts.** If any concept is labeled `[SEED]` or `[SEED-TECH]`:
   - `[SEED]` is UNTOUCHABLE — never merge, edit, rephrase, or remove it. It must appear in the output with its core value proposition intact from seed.md.
   - `[SEED-TECH]` concepts must not be merged into non-seed concepts, but can absorb duplicates of themselves.
   - Preserve all seed labels in the deduplicated output.

4. **Merge overlapping concepts.** When two non-seed concepts overlap, combine them into one entry. Keep the best phrasing from each. Note which originals were merged.

5. **Assign an ID** to each unique concept (S-01, S-02, etc.) for reference by downstream agents.

6. **Output the deduplicated list.** Target: 15-25 unique concepts (fewer in seed-only mode). Don't score, rank, or filter.

## Output format

```markdown
# Idea Dedup — [Segment Name]

*Date: [today]*

## Deduplicated Concepts

| ID | Name | Description | Source(s) | Label |
|---|---|---|---|---|
| S-01 | [name] | [1-2 sentence description] | idea-volume #1 | [SEED] |
| S-02 | [name] | [description] | idea-volume #3, idea-tech AI | |
| S-03 | [name] | [description] | idea-volume #12, idea-volume #15 (merged) | |
| S-04 | [name] | [description] | idea-tech Mobile | [SEED-TECH] |

[Continue for all concepts]

## Merge Log

| Merged Into | Original Concepts | Reason |
|---|---|---|
| S-03 | idea-volume #12, idea-volume #15 | [why they're the same concept] |

## Stats

- Input concepts: [X] (idea-volume) + [X] (idea-tech) + [X] (prior-art novel)
- After dedup: [X] unique concepts
- Merged: [X] pairs
- Seed concepts preserved: [X]
```

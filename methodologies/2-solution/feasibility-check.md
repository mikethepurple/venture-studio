# Feasibility Check

<!-- model: haiku -->

## When to use

Always runs in step 2 (wave 3). Scores each solution concept on build complexity and feasibility. Does not assess impact or differentiation — only how hard it is to build.

## Inputs needed

- brief.md
- idea-dedup.md
- idea-mutation.md
- prior-art.md

## Process

1. **Collect all concepts** from idea-dedup.md and idea-mutation.md.

2. **For each concept, assess build complexity:**
   - What are the core technical components? (frontend, backend, AI model, data pipeline, integrations, hardware)
   - What hard dependencies exist? (third-party APIs, datasets, regulatory approval, partnerships)
   - Does prior art show this is buildable? (existing products = proven feasible)
   - What's the minimum viable version? Could a stripped-down version ship in 2 weeks?

3. **Score each concept /5 on feasibility:**
   - 5 = buildable in 2 weeks by one developer, no hard dependencies
   - 4 = buildable in 4 weeks, minor dependencies (common APIs, standard infra)
   - 3 = buildable in 8 weeks, some hard dependencies or specialized knowledge
   - 2 = buildable in 3+ months, significant dependencies or novel tech
   - 1 = requires breakthrough tech, major partnerships, or regulatory approval

4. **Estimate build timeline:** 2-week / 4-week / 8-week / 3-month+ for each concept.

5. **Flag hard blockers** — anything that makes a concept unbuildable regardless of time (e.g., requires data that doesn't exist, needs hardware manufacturing).

## Output format

```markdown
# Feasibility Check — [Problem Name]

*Date: [today]*

## Feasibility Scores

| ID | Concept | Feasibility /5 | Timeline | Hard Dependencies | Blockers |
|---|---|---|---|---|---|
| S-01 | [name] | [X]/5 | [2wk/4wk/8wk/3mo+] | [dependencies or "none"] | [blockers or "none"] |
| S-02 | [name] | [X]/5 | [timeline] | [dependencies] | [blockers] |
| M-01 | [name] | [X]/5 | [timeline] | [dependencies] | [blockers] |

[Continue for all concepts]

## Blocked Concepts

[List any concepts with hard blockers and why they're unbuildable]

## Fastest to Ship

[Top 5 concepts by feasibility score — the quickest path to a testable product]
```

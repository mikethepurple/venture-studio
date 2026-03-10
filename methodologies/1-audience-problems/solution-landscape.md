# Solution Landscape

## When to use

Always runs in step 1 (wave 2). Maps the existing commercial landscape — what products, tools, and services currently exist for this audience? This is NOT a deep competitive analysis (that happens in step 3). It's a lightweight scan of "how is this currently solved?" to inform ideation in step 2.

## Inputs needed

- brief.md
- community-mapping.md

## Process

1. **Search for existing commercial products** that serve this audience:
   - Search Google for "[audience] tools," "[audience] software," "[audience] app"
   - Search Product Hunt for relevant products
   - Search app stores (iOS/Android) for relevant apps
   - Check G2, Capterra, or similar review sites for software categories

2. **For each product found, record:**
   - Name and URL
   - What it does (which problems it addresses)
   - Pricing tier (free / freemium / paid — note the price)
   - Quality signals (ratings, review count, last updated)
   - Target user (consumer, practitioner, enterprise)

3. **Categorize by solution approach:**
   - Group products into categories (e.g., "self-service apps," "professional software," "hardware," "educational platforms," "marketplace/directory")
   - Note which categories are crowded vs. sparse

4. **Identify the gap map:**
   - Which audience needs have many products? (saturated)
   - Which audience needs have few or no products? (underserved)
   - Which existing products are poorly rated or abandoned? (execution gap)

5. **Don't do deep analysis.** Just map what exists with quality signals. Step 3 (opportunity validation) will do the deep competitive research.

## Output format

```markdown
# Solution Landscape — [Audience]

*Date: [today]*

## Existing Products

### Category: [e.g., Consumer Apps]

| Product | URL | What it does | Price | Rating | Users/Downloads | Last Updated |
|---|---|---|---|---|---|---|
| [name] | [url] | [1-line] | [price] | [X/5] | [count] | [date] |

### Category: [e.g., Professional Software]

| Product | URL | What it does | Price | Rating | Users/Downloads | Last Updated |
|---|---|---|---|---|---|---|
| [name] | [url] | [1-line] | [price] | [X/5] | [count] | [date] |

[Continue for each category]

## Gap Map

| Audience Need | Products Found | Quality | Assessment |
|---|---|---|---|
| [need] | [count] | [good/poor/none] | Saturated / Underserved / Execution gap |

## Key Observations

- [2-3 bullets: what's the overall landscape health? Where are the biggest gaps?]

## Sources Used

- [URL — must match a citation above]
```

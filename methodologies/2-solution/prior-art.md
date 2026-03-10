# Prior Art
<!-- model: haiku -->


## When to use

Always runs in step 2 (wave 1). Searches for existing products, tools, and workarounds that already solve this problem. Catalogues what exists without evaluating it.

## Inputs needed

- brief.md
- step-1/decisions.md

## Process

1. **Direct competitors:** Search for products and services explicitly marketing to this problem. Record name, URL, pricing, founding year, and one-line description.

2. **Adjacent tools:** Search for products solving a related or broader problem that partially cover this use case. Note which part of the problem they address.

3. **DIY workarounds:** Search for spreadsheet templates, Notion templates, Zapier automations, browser extensions, and manual workflows people have built. Check Reddit, Product Hunt, GitHub, Gumroad.

4. **Open-source alternatives:** Search GitHub for open-source projects tackling this problem. Note stars, last commit date, and contributor count.

5. **Dead products:** Search for products that attempted this and shut down. Check Crunchbase, Product Hunt graveyard, TechCrunch shutdown announcements. Note why they failed if known.

6. **Compile the catalogue.** List everything found. Don't rank, score, or evaluate — just document what exists.

## Output format

```markdown
# Prior Art — [Problem Name]

*Date: [today]*

## Direct Competitors

| Product | URL | Pricing | Founded | Description |
|---|---|---|---|---|
| [name] | [url] | [pricing] | [year] | [one line] |

## Adjacent Tools

| Product | URL | Overlap | Gap |
|---|---|---|---|
| [name] | [url] | [what it covers] | [what it doesn't] |

## DIY Workarounds

- [workaround description] — [source/URL]

## Open-Source Alternatives

| Repo | Stars | Last Commit | Contributors | Description |
|---|---|---|---|---|
| [name] | [X] | [date] | [X] | [one line] |

## Dead Products

| Product | Shut Down | Reason (if known) | Source |
|---|---|---|---|
| [name] | [year] | [reason] | [URL] |

## Sources Used

- [URL — must match a citation above]
```

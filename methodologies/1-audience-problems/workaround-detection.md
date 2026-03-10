# Workaround Detection

## When to use

Always runs in step 1 (wave 2). Searches for DIY solutions, templates, and manual workarounds the audience has built. DIY = strong problem signal — people care enough to build their own solution.

## Inputs needed

- brief.md
- community-mapping.md

## Process

1. **Search for DIY workarounds** across these categories:
   - **Spreadsheet templates** — search Google, Reddit, and communities for "[audience topic] spreadsheet template," "[task] Google Sheets," "[task] Excel template"
   - **Notion templates** — search Notion template gallery and Google for "[topic] Notion template"
   - **Airtable bases** — search Airtable universe for relevant bases
   - **Zapier/Make automations** — search for "[task] Zapier" or "[task] automation"
   - **Browser extensions** — search Chrome Web Store for audience-relevant extensions
   - **GitHub repos** — search for scripts, tools, or utilities the audience has built
   - **Gumroad/Etsy digital products** — search for templates, guides, toolkits sold to this audience

2. **For each workaround found, record:**
   - What it does (the problem it solves)
   - Where it was found (URL)
   - Complexity (simple template vs elaborate system)
   - Adoption signals (downloads, stars, purchases, comments)
   - Price (free or paid — paid workarounds = very strong signal)

3. **Search communities** from community-mapping.md for posts sharing workarounds ("I built a spreadsheet for," "here's my system for," "I automated this with").

4. **Don't score or rank.** Just catalogue what people have built.

## Output format

```markdown
# Workaround Detection — [Audience]

*Date: [today]*

## Workarounds Found

### W-01: [What it solves]
**Type:** Spreadsheet / Notion / Zapier / Extension / Script / Digital product
**URL:** [link]
**Complexity:** [simple/moderate/elaborate]
**Adoption:** [downloads/stars/purchases/comments]
**Price:** [free / $X]

### W-02: [What it solves]
**Type:** [type]
**URL:** [link]
**Complexity:** [level]
**Adoption:** [signals]
**Price:** [free / $X]

[Continue for all workarounds found]

## Community-Shared Workarounds

- "[quote about their workaround]" — [source/URL] `[primary]`

## Summary

| Problem Area | Workarounds Found | Paid? | Strongest Signal |
|---|---|---|---|
| [problem] | [X] | [yes/no] | [most-adopted workaround] |

## Sources Used

- [URL — must match a citation above]
```

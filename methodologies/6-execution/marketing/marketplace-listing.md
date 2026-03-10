# Marketplace Listing

## When to use

Runs in step 6 execution. Identifies relevant marketplaces and produces listing copy, pricing, and SEO keywords for each platform. For physical goods, digital products, or services that can be listed on third-party marketplaces.

## Inputs needed

- brief.md
- step-4/decisions.md (business model, value prop, pricing)
- Any landing page or product URL from the current iteration's build output

## Process

1. **Identify relevant marketplaces** for this product type:
   - **Digital products:** Gumroad, AppSumo, LemonSqueezy, Etsy (digital), Creative Market
   - **SaaS/tools:** Chrome Web Store, Shopify App Store, Slack App Directory, Notion integrations
   - **Physical products:** Amazon, Etsy, eBay, niche marketplaces for the category
   - **Services:** Upwork, Fiverr, Contra (if productized service)
   - **Templates/resources:** ThemeForest, Canva marketplace, Figma community
   - Select 2-4 marketplaces with the best audience fit

2. **For each selected marketplace, write listing copy:**
   - **Title:** Marketplace-optimized (include primary keyword, stay within character limits)
   - **Description:** Short version (1-2 sentences for search results) + long version (full listing)
   - **Bullet points / features:** 5-7 key features in the marketplace's format
   - **Category / tags:** The right category and all relevant tags

3. **Pricing strategy per marketplace:**
   - Research competing listings on each marketplace for price benchmarking
   - Recommend a price point (can differ per marketplace based on audience expectations)
   - Note marketplace fees and commissions

4. **SEO keywords per marketplace:**
   - 10-15 keywords per platform (marketplace search algorithms differ from Google)
   - Research what competing listings rank for
   - Include long-tail keywords specific to the use case

5. **Image/media specs per marketplace:**
   - Required image dimensions and count
   - Video requirements (if applicable)
   - Describe what each image should show

## Output format

```markdown
# Marketplace Listing — [Product Name]

*Date: [today]*

## Selected Marketplaces

| Marketplace | Why | Audience Fit | Fee Structure |
|---|---|---|---|
| [name] | [rationale] | [high/medium] | [X% commission or $X/mo] |

## Listing: [Marketplace 1]

**Title:** [optimized title]
**Short description:** [1-2 sentences]
**Long description:**
> [full listing description]

**Features:**
1. [feature]
2. [feature]
[5-7 features]

**Category:** [category]
**Tags:** [tag1], [tag2], [tag3]

**Price:** $[X] — [rationale based on competitor benchmarks]
**Competitor prices:** [range found on this marketplace]

**SEO Keywords:**
[15 keywords, comma-separated]

**Image Specs:**
| Image | Dimensions | Content |
|---|---|---|
| Hero | [WxH] | [what to show] |
| Feature 1 | [WxH] | [what to show] |

---

## Listing: [Marketplace 2]

[same structure]

## Cross-Marketplace Strategy

- **Price consistency:** [same price everywhere or differentiated — and why]
- **Launch order:** [which marketplace first and why]
- **Cross-promotion:** [how listings can reference each other]
```

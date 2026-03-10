<!-- model: sonnet -->

# Landing Page Builder

## When to use

Runs in step 6 execution. Builds and deploys a conversion-optimized landing page for validation. Supports waitlist and preorder goals.

## Inputs needed

- brief.md
- step-3/decisions.md (selected solution)
- step-4/decisions.md (business model, pricing)
- step-5/*.md (metrics, success criteria)

## Process

1. **Extract the brief** from prior step outputs:
   - Product name and one-line description (from solution design)
   - Target customer persona (from brief + problem discovery)
   - Key value prop (from business model)
   - CTA goal: waitlist or preorder (from business model — if price is defined, use preorder; otherwise waitlist)
   - Price point if preorder (from business model)

2. **Build a Next.js + Tailwind landing page** with this structure:

   **Above the fold:**
   - Headline: what it does for who (e.g., "Automated inventory alerts for Shopify stores")
   - Sub-headline: the key benefit or insight
   - CTA: one clear action (Join waitlist / Pre-order at $X)

   **Below the fold:**
   - Problem section: "If you've ever [pain]..." — make the reader nod
   - How it works: 3 steps max
   - Benefits: 3 bullets, outcomes not features
   - FAQ: address 3 common objections
   - Final CTA: same as above the fold

3. **Design rules:**
   - One goal per page — no navigation, no external links
   - Mobile-first — most paid traffic converts on mobile
   - Load time < 2 seconds
   - Plain language a 10-year-old would understand

4. **Tracking requirements:**
   - Google Analytics 4 via gtag.js with conversion event on form submit
   - UTM parameter passthrough
   - Thank-you state (inline confirmation, no redirect)

5. **For waitlist:** Email input + submit button. Store via API route.
   **For preorder:** Stripe Checkout link. Button: "Pre-order — $[X]". Track checkout_initiated and purchase_complete events.

6. **File structure:**
   ```
   landing-page/
     app/page.tsx
     app/layout.tsx
     app/api/subscribe/route.ts (waitlist)
     public/og-image.png (placeholder)
     package.json
     tailwind.config.ts
     next.config.ts
   ```

7. **Deploy** to Vercel if configured (`vercel --prod`). Otherwise provide deployment instructions.

## Output format

Write the complete codebase to the output directory. Also write a notes file:

```markdown
# Landing Page — Notes

**URL:** [live URL or "not deployed — run vercel --prod"]
**CTA:** [waitlist / preorder at $X]
**Tracking:** [GA4 event name for conversion]
**Manual steps:** [any setup the user needs to do — Stripe product, GA4 property, etc.]
```

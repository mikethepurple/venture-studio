<!-- model: sonnet -->

# Product Builder

## When to use

Runs in step 6 execution. Builds a minimum viable product when the value is experiential (can't be captured by a landing page) or when activation/retention is the validation goal.

## Inputs needed

- brief.md
- step-3/decisions.md (selected solution)
- step-4/decisions.md (business model)
- step-5/*.md (metrics, activation definition)

## Process

1. **Extract the scope** from prior step outputs:
   - Core job-to-be-done (one sentence from solution design)
   - Activation definition (what success looks like for user on day 1 — from metrics)
   - User flow from signup to activated
   - What is explicitly OUT of scope

2. **Scope the MVP with these principles:**
   - Build the minimum version that delivers the core value — not a demo, a working product
   - Cut all configuration (use opinionated defaults)
   - Cut admin panels (use Airtable/Notion for ops)
   - Cut billing (Stripe links or free for first 10 users)
   - Cut onboarding flows (manual via email/call)
   - Cut analytics dashboards (use GA4/Mixpanel)

3. **Default tech stack:**
   | Layer | Choice |
   |---|---|
   | Framework | Next.js 14 (App Router) |
   | Styling | Tailwind CSS |
   | Auth | Clerk |
   | Database | Supabase (Postgres) |
   | AI (if needed) | Anthropic SDK (Claude) |
   | Payments | Stripe |
   | Deploy | Vercel |

4. **Build order:**
   - Project scaffold
   - Core data models (minimum tables)
   - Activation flow (signup to first value moment)
   - Analytics instrumentation (GA4 custom events)
   - Basic UI (functional > beautiful)
   - Deploy + smoke test

5. **Wire GA4 custom events:**
   - `signup_complete`
   - `onboarding_complete`
   - `activation` (the defined activation moment)

6. **Deploy to Vercel.** Return live URL.

## Output format

Write the complete codebase to the output directory. Also write a notes file:

```markdown
# Product — Notes

**URL:** [live URL or deployment instructions]
**Activation definition:** [what counts as activated]
**What's built:** [brief list]
**What's NOT built (intentional):** [what was cut and why]
**Manual ops:** [what the founder needs to handle manually for first 10 users]
**Tracking:** [GA4 events configured]
```

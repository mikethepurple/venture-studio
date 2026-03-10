# Competitive Response

<!-- model: sonnet -->

## When to use

Always runs in step 4 (wave 2). War-games how competitors, regulators, and platforms would react to this solution entering the market. Identifies strategic threats that the revenue model and GTM don't account for.

## Inputs needed

- brief.md
- step-3/decisions.md
- step-3/{item-slug}/competitor-mapping.md
- step-3/{item-slug}/scout-enrichment.md
- revenue-model.md
- gtm-strategy.md

## Process

1. **Read all inputs.** Build a complete picture of the competitive landscape from competitor-mapping.md and scout-enrichment.md, plus the proposed business model and GTM from wave 1 outputs.

2. **War-game competitor reactions.** For each major competitor (top 5 from competitor-mapping.md):
   - **What would they do if this solution gained traction?**
     - Copy the feature/approach? (How fast? Do they have the capability?)
     - Cut prices to compete? (Can they afford to? What's their margin?)
     - Acquire or acqui-hire? (Do they have the resources?)
     - Partner/integrate to neutralize? (Is this likely?)
     - Ignore? (How big does this solution need to get before they notice?)
   - **What's their unfair advantage?** (existing users, capital, technology, regulatory position)
   - **What's their likely timeline to respond?** (months)

3. **Analyze platform risk.** For each platform dependency:
   - **Telegram:** Policy changes (Mini App restrictions, payment rules, crypto stance), API changes, competing features (Telegram building its own prediction feature?)
   - **TON blockchain:** Technical risks, governance changes, validator economics, smart contract risks
   - **USDT/Tether:** Regulatory crackdown, de-pegging risk, OFAC sanctions expansion
   - **App stores:** If expanding beyond Telegram, Apple/Google policy on prediction markets and crypto

4. **Model regulatory threats.** For each target geography:
   - **Russia:** Crypto regulation timeline (July 2026), gambling law application to prediction markets, data localization requirements, sanctions escalation risk
   - **Kazakhstan:** AIFC regulatory stance, crypto licensing requirements
   - **Georgia:** Virtual zone regulations, potential gambling classification
   - **Armenia:** Current 0% crypto gains, risk of policy change, EU alignment implications
   - **Global:** OFAC expansion, EU MiCA implications, cross-border regulatory arbitrage risks

5. **Identify second-order threats.** Beyond direct competition:
   - Market incumbents pivoting (1xBet adding prediction markets, crypto exchanges adding prediction features)
   - New entrants (well-funded startups, crypto projects with token incentives)
   - Technology shifts (AI predictions commoditizing the product, on-chain AMMs making middleware unnecessary)
   - Macro events (crypto winter, sanctions escalation, CIS political instability)

6. **Score each threat.** Rate probability (1-5) and impact (1-5), calculate risk score.

## Output format

```markdown
# Competitive Response — [Solution Name]

*Date: [today]*

## Competitor War Games

### [Competitor 1 Name]
- **Current position:** [market share, funding, capabilities]
- **Most likely response:** [what they'd do]
- **Response timeline:** [X months]
- **Their advantage:** [unfair advantage]
- **Our defense:** [what protects this solution]
- **Threat level:** [critical/high/medium/low]

### [Competitor 2 Name]
[same structure]

[repeat for top 5 competitors]

## Platform Risk Assessment

| Platform | Risk | Probability /5 | Impact /5 | Risk Score | Timeline |
|---|---|---|---|---|---|
| Telegram | [specific risk] | [X] | [X] | [X] | [when] |
| TON | [specific risk] | [X] | [X] | [X] | [when] |
| USDT | [specific risk] | [X] | [X] | [X] | [when] |
| [other] | [specific risk] | [X] | [X] | [X] | [when] |

### Platform Risk Details

#### Telegram
- **Specific scenarios:** [what could go wrong]
- **Precedents:** [has Telegram done this before?]
- **Mitigation:** [what can be done]

[repeat for each platform]

## Regulatory Threat Matrix

| Country | Threat | Probability /5 | Impact /5 | Risk Score | Timeline |
|---|---|---|---|---|---|
| Russia | [specific regulatory risk] | [X] | [X] | [X] | [when] |
| Kazakhstan | [risk] | [X] | [X] | [X] | [when] |
| Georgia | [risk] | [X] | [X] | [X] | [when] |
| Armenia | [risk] | [X] | [X] | [X] | [when] |
| Global/OFAC | [risk] | [X] | [X] | [X] | [when] |

### Regulatory Details

#### [Country]
- **Current status:** [relevant laws/regulations]
- **Pending changes:** [upcoming legislation]
- **Worst case:** [what happens if regulation is hostile]
- **Best case:** [what happens if regulation is favorable]

## Second-Order Threats

| Threat | Category | Probability /5 | Impact /5 | Risk Score |
|---|---|---|---|---|
| [threat] | [incumbent pivot / new entrant / tech shift / macro] | [X] | [X] | [X] |

## Threat Summary

| Rank | Threat | Risk Score (/25) | Category | Urgency |
|---|---|---|---|---|
| 1 | [top threat] | [X] | [competitive/platform/regulatory/macro] | [immediate/6mo/12mo] |
| 2 | [threat] | [X] | [category] | [urgency] |
| 3 | [threat] | [X] | [category] | [urgency] |

**Overall competitive defensibility:** [strong / moderate / weak] — [one-sentence assessment]

## Sources Used

- [URL — must match a citation above]
```

# CRO report template

Use this structure. Keep the executive summary to one screen. Number every recommendation, because the user will choose items by number.

```markdown
# CRO Audit — [Store name] ([domain])
[Date] · Platform: [Shopify/…] · Pages reviewed: [list] · Devices: mobile + desktop

## Executive summary
- Overall: [2–3 sentences on the biggest themes, e.g. "Trust and cost transparency are the main leaks; the PDP hides its strongest proof below the fold."]
- Top 3 quick wins: #1, #2, #3
- Data used: [analytics / heatmaps / none — heuristic audit; treat items as hypotheses]
- Assumptions: [anything you assumed because no one was there to ask]

## Scorecard
| Area | Score (1–5) | Main issue |
|---|---|---|
| Header & trust | | |
| Homepage | | |
| Navigation / mega menu | | |
| Collection pages | | |
| Product page | | |
| Cart | | |
| Checkout | | |
| Technical / speed / schema | | |

## Prioritised recommendations
| # | Page | Recommendation | Impact | Confidence | Ease | ICE | Type |
|---|---|---|---|---|---|---|---|
| 1 | PDP | Add a trust bar + review count above the fold | 4 | 4 | 5 | 13 | Quick win |
| … | | | | | | | Quick win / Test / Project |

Type: **Quick win** = low risk, ship directly · **Test** = contested or high-stakes, A/B test it · **Project** = bigger build

## Detail
### #1 — [Title]
- **Where:** [page › section] (screenshot ref)
- **What we saw:** [specific observation]
- **Why it matters:** [principle + source, e.g. ATIDFA "Attention" (Kenyon); Baymard: 19% abandon over trust]
- **Recommendation:** [specific build spec]
- **Hypothesis:** Because [X], changing [Y] should improve [metric].
- **How to measure:** [primary RPV; secondary add-to-cart rate…; test vs before/after]
- **Effort / notes:** [apps needed, data required (real reviews/stock), risks]

(repeat)

## Contested items — test, don't assume
[Free-shipping threshold, scarcity cues, recently viewed, quick add, etc. Explain why.]

## Measurement plan
- Primary metric: revenue per visitor. Secondary: add-to-cart rate, checkout-start rate, AOV.
- Tracking gaps found: [...]
- Test duration: ≥2 full weeks; segment by device and new vs returning.

## Next step
Reply with which to implement: **all**, **quick wins only**, **specific numbers** (e.g. 1, 3, 5–8), or **none**.
```

## Scoring guide
- **Impact**: how much traffic sees it × how close it is to the purchase decision. Cart and PDP items usually beat homepage items.
- **Confidence**: is there evidence on this site (data, heatmaps), or only strong external evidence (Baymard, repeated practitioner wins)? Lower it for contested items.
- **Ease**: 5 = a theme setting or copy change; 3 = a new section or app; 1 = a custom build or a platform change.

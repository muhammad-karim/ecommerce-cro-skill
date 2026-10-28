---
name: ecommerce-cro
description: Audit an e-commerce site or landing page for conversion rate optimisation (CRO), produce a prioritised report of recommendations, then implement the changes the user approves. Built on Oliver Kenyon's ATIDFA framework and redesign patterns, Kurt Elster's split-test findings, and Baymard-style checkout research. Use this whenever someone asks for a CRO audit, conversion review, "why isn't my store converting", a landing page or product page teardown, ideas to raise conversion rate, AOV or revenue per visitor, or wants to fix their Shopify, WooCommerce or other store's homepage, collection pages, product pages, cart or checkout — even if they don't say "CRO".
---

# E-commerce CRO: evaluate → report → approve → implement

This skill runs in three phases, with a hard stop between them:

1. **Evaluate** the site against a proven checklist.
2. **Report** prioritised recommendations, each with evidence and a hypothesis.
3. **Ask** which to implement (all, some, or none). Then **execute** only what was approved, and verify.

The stop matters because CRO changes touch a live revenue stream. The owner must choose what ships.

## Reference files (read as needed)

| File | Read when |
|---|---|
| `references/page-checklists.md` | Always, during the evaluation. The core checklist, page by page |
| `references/oliver-kenyon.md` | Always. ATIDFA framework, above-the-fold rules, his recurring redesign fixes and recent test wins |
| `references/kurt-elster.md` | Always. Test-first mindset, readability rules, and his split-test results (some contradict "best practice") |
| `references/research-and-benchmarks.md` | When sizing impact, checking checkout friction, or the site sells to AI shopping agents |
| `references/report-template.md` | When writing the report |
| `references/implementation.md` | Before changing anything, once the user has approved items |

## Phase 0 — Scope (keep it quick)

Find out, or infer and state your assumptions:
- **URL(s)** and the **platform** (Shopify, WooCommerce, WordPress, BigCommerce, custom/static, landing page builder). Check page source for clues like `cdn.shopify.com` or `wp-content`.
- **The goal**: conversion rate, AOV, revenue per visitor (RPV), or leads. Default to RPV. Conversion rate alone misleads because it ignores order value.
- **Traffic and data**: monthly sessions, current conversion rate and AOV, top traffic sources, analytics access, and any heatmaps or session recordings. Without data, say the audit is heuristic and the recommendations are hypotheses to test.
- **What implementation access exists**: theme code or repo, a CMS connector, or none (then the output is a developer brief).

Ask at most one or two questions. If the user is not present, proceed with sensible defaults and list them at the top of the report.

## Phase 1 — Evaluate

Audit the purchase path in the order a shopper meets it, **mobile first** (most traffic is mobile; check desktop second):

1. Announcement bar, header and trust bar
2. Homepage
3. Navigation and mega menu (mobile menu too)
4. Collection or category page (sort order, filters, product cards)
5. Product page (PDP), above the fold, then the rest of the page
6. Cart and cart drawer
7. Checkout entry (don't place orders or enter payment details)
8. Any paid-traffic landing pages, if the user names them

**How to look at pages.** Use the best tool available:
- A browser tool (built-in browser or Claude in Chrome) lets you see layout, take screenshots at mobile width (~390px) and desktop, open the cart and menu, and check what sits above the fold. This is strongly preferred, because most CRO issues are visual.
- WebFetch or page source tells you content, structure, schema markup and apps, but not layout. If this is all you have, say so in the report.
- Theme or source code, if you have it, shows exactly how sections are built and makes estimates of the work reliable.

Pick 1–2 representative products (a best seller and a higher-priced item) and one main collection.

For each page, run through its checklist in `page-checklists.md` and apply the ATIDFA lens from `oliver-kenyon.md`. Record each finding with:
- **Where** (page and section) and **what you saw**. Use a screenshot reference or a specific detail, not a vague impression.
- **Why it matters**: the principle, and the source if one applies.
- **The fix**: specific enough that someone could build it.

Also run quick technical checks: page speed (PageSpeed Insights, if reachable), broken elements, readability (font size, contrast, line length), and Product schema / structured data.

Ground findings in what you actually observed. A recommendation that sounds plausible but doesn't match the page wastes the owner's time and erodes trust in the rest of the report.

## Phase 2 — Report

Write the report using `references/report-template.md`. Key rules:

- **Prioritise with ICE** (Impact, Confidence, Ease, each 1–5). Sort by score. Quick wins (high impact, high ease) go first.
- **Every recommendation is a hypothesis.** Format it as "Because we saw X, we believe changing Y will improve Z (metric)". Kurt Elster's results show that "best practices" often lose in testing, so frame changes as tests where traffic allows. Use roughly 15–20k monthly sessions as the rough threshold for meaningful A/B tests. Below that, ship low-risk fixes directly and monitor before and after.
- **Flag the contested ones.** Free-shipping thresholds, urgency and scarcity, recently viewed widgets, add-to-cart on collection pages, and removing breadcrumbs all have mixed evidence. Say so, and recommend testing over shipping blind.
- **Never fabricate.** No fake urgency ("only 2 left" when untrue), no invented reviews or customer counts, no unearned "as seen in" logos. Fake scarcity and fake social proof break consumer protection law in the UK, EU and US. Where a recommendation needs real data (review counts, stock levels), say it must come from the store's real data.
- Keep it scannable: an executive summary up top, a table of recommendations, then detail per item.

Deliver the report as a document the user can keep: an artifact or doc where available, otherwise a markdown file. Then summarise the top 3–5 items in chat.

## Phase 3 — Ask, then execute

After the report, **stop and ask** which recommendations to implement. Use AskUserQuestion if available, with options such as: "All quick wins", "All recommendations", "Let me pick (by number)", "None, report only". If they pick, let them reply with the item numbers.

Do not start implementing until they answer. If running unattended, finish at the report and leave the question for when they return.

Once approved, follow `references/implementation.md`:
1. **Work on a copy, never the live site.** Duplicate the Shopify theme, use a staging site or git branch, or a draft page.
2. Implement items **one at a time**, in priority order, with small reviewable changes.
3. Use the store's **real data** for social proof, stock and prices.
4. **Verify each change** at mobile and desktop widths. Check that nothing broke: cart, add-to-cart and variant selection.
5. Hand back a preview link, a change log (what changed, where, how to revert), and a **measurement plan**: the primary metric (RPV), secondary metrics (add-to-cart rate, checkout starts), and a test duration of at least 2 full weeks, to cover pay cycles.
6. Publishing to live is the owner's decision. Ask before publishing, and never publish without an explicit yes.

If you have no write access, produce a developer-ready brief for each approved item: what to change, where, acceptance criteria, and QA steps. Say what access would let you do it directly.

## Attribution

Principles are paraphrased from Oliver Kenyon (ConversionWise), Kurt Elster (Ethercycle / The Unofficial Shopify Podcast) and Baymard Institute research. Source links are in each reference file. Revenue figures quoted in the references are self-reported by the practitioners. Present them as examples, not guarantees.

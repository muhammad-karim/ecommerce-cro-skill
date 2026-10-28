---
name: ecommerce-cro
description: Audit an online store or landing page to find what's stopping visitors from buying, write a clear prioritised report of fixes, then make the changes the owner approves. Uses the latest e-commerce conversion rate optimisation (CRO) best practice and experiment results. Use this whenever someone asks for a CRO audit or conversion review, asks "why isn't my store converting", wants a product page, landing page, cart or checkout reviewed, wants ideas to get more sales, a higher order value or more revenue per visitor, or wants to improve their Shopify, WooCommerce or other store, even if they don't say "CRO".
---

<!--
  HOW THIS SKILL WORKS (a note for people reading this file)

  This file tells Claude how to run a CRO audit. It works in three steps:

    1. LOOK   - Claude visits the store and checks each page against a
                checklist of what makes shoppers buy (or leave).
    2. REPORT - Claude writes a report listing every fix, ranked so the
                quickest, highest-impact wins come first.
    3. ASK, THEN BUILD - Claude asks which fixes you want. Nothing changes
                until you choose. It then builds only those, on a copy of
                your site, never on the live one.

  The detailed knowledge (checklists, proven page patterns, test results,
  report layout, how to make changes safely) lives in the references/
  folder. Claude reads those files when it needs them.
-->

# E-commerce CRO: look → report → ask → build

This skill runs in three phases, with a **hard stop** between the report and any changes.

1. **Evaluate** the site against a proven checklist.
2. **Report** prioritised recommendations, each with evidence and a hypothesis.
3. **Ask** which to implement (all, some, or none). Then **execute** only what was approved, and verify it.

The stop matters because CRO changes touch a live revenue stream. The owner must choose what ships.

## Reference files (read as needed)

<!-- These are the skill's "knowledge base". Claude loads them only when needed, to keep things fast. -->

| File | What's in it | Read when |
|---|---|---|
| `references/page-checklists.md` | The page-by-page audit checklist | Always, during the evaluation |
| `references/proven-page-patterns.md` | The ATIDFA page framework, above-the-fold rules, common fixes, recent experiment results | Always |
| `references/testing-insights.md` | Split-test results that contradict popular "best practice", readability rules, customer research methods | Always |
| `references/research-and-benchmarks.md` | Checkout abandonment data, A/B testing realities, getting ready for AI shopping assistants | When sizing impact or reviewing checkout |
| `references/report-template.md` | The report layout and how to score each fix | When writing the report |
| `references/implementation.md` | How to make changes safely on Shopify, WordPress, code repos and page builders | Before changing anything, once the user has approved items |

## Phase 0 — Scope (keep it quick)

<!-- Claude gathers just enough context to do a good job, without quizzing the owner. -->

Find out, or infer and state your assumptions:

- **URL(s)** and **platform** (Shopify, WooCommerce, WordPress, BigCommerce, custom/static, landing page builder). Page source gives clues, e.g. `cdn.shopify.com` or `wp-content`.
- **Goal:** conversion rate, average order value (AOV), revenue per visitor (RPV), or leads. Default to RPV. Conversion rate alone can mislead because it ignores how much people spend.
- **Traffic and data:** monthly sessions, current conversion rate and AOV, top traffic sources, analytics access, heatmaps or session recordings. Without data, say the audit is based on best practice and the recommendations are hypotheses to test.
- **What implementation access exists:** theme code or repo, a CMS connector, or none (in which case the output is a developer brief).

Ask at most one or two questions. If the user isn't present, use sensible defaults and list them at the top of the report.

## Phase 1 — Evaluate

<!-- Claude walks the site the way a shopper would, starting on a phone, because most shoppers do. -->

Audit the purchase path in the order a shopper meets it, **mobile first** (most traffic is mobile), then desktop:

1. Announcement bar, header, trust bar
2. Homepage
3. Navigation and mega menu (including the mobile menu)
4. Collection/category page (sort order, filters, product cards)
5. Product page (PDP): above the fold, then the rest of the page
6. Cart / cart drawer
7. Checkout entry (don't place orders or enter payment details)
8. Paid-traffic landing pages, if the user names any

**How to look at pages.** Use the best tool available:

- **A browser** (built-in browser or Claude in Chrome) lets you see the layout, take screenshots at mobile width (~390px) and desktop, open the cart and menu, and check what sits above the fold. Strongly preferred, because most CRO issues are visual.
- **WebFetch or page source** gives content, structure, schema markup and installed apps, but not layout. If this is all you have, say so in the report.
- **Theme or source code**, if available, shows exactly how sections are built and makes effort estimates reliable.

Pick one or two representative products (a best seller and a higher-priced item) and one main collection.

For each page, work through its checklist in `page-checklists.md`. Apply the ATIDFA lens from `proven-page-patterns.md` (Attention → Transformation → Interest → Desire → FAQ → Action: the order a persuasive page should flow in). Record each finding with:

- **Where** (page and section) and **what you saw**: a screenshot reference or a specific detail, not a vague impression.
- **Why it matters**: the principle or evidence behind it.
- **The fix**: specific enough that someone could build it.

Also run quick technical checks: page speed (PageSpeed Insights, if reachable), broken elements, readability (font size, contrast, line length), and product structured data.

Ground every finding in what you actually observed. A plausible-sounding recommendation that doesn't match the page wastes the owner's time and makes them distrust the rest of the report.

## Phase 2 — Report

<!-- The report is designed to be skimmed: summary first, then a ranked table, then detail for each fix. -->

Write the report using `references/report-template.md`. Key rules:

- **Rank the fixes.** Score each one for Impact, Confidence and Ease (1–5 each), then sort by the total. Quick wins (high impact, easy to do) go first.
- **Treat every recommendation as a hypothesis**: "Because we saw X, we believe changing Y will improve Z." Real test data shows that popular "best practices" often lose, so frame changes as tests where traffic allows. As a rough guide, A/B tests need around 15–20k monthly sessions. Below that, ship low-risk fixes directly and compare before and after.
- **Flag the contested ones.** Free-shipping thresholds, urgency and scarcity messages, "recently viewed" widgets, quick add-to-cart on collection pages and removing breadcrumbs all have mixed evidence. Say so, and recommend testing over shipping blind.
- **Never fabricate.** No fake urgency ("only 2 left" when it isn't true), no invented reviews or customer counts, no "as seen in" logos the brand hasn't earned. Fake scarcity and fake social proof break consumer protection law in the UK, EU and US. Where a fix needs real data (review counts, stock levels), say it must come from the store's real data.
- Keep it scannable: executive summary, a table of recommendations, then detail per item.

Deliver the report as a document the user can keep (an artifact or doc where available, otherwise a markdown file), then summarise the top 3–5 items in chat.

## Phase 3 — Ask, then execute

<!-- Nothing is changed until the owner says which fixes they want. -->

After the report, **stop and ask** which recommendations to implement. Use AskUserQuestion if available, with options like "All quick wins", "All recommendations", "Let me pick (by number)", "None, report only". Let them reply with item numbers.

Do not start implementing until they answer. If running unattended, finish at the report and leave the question waiting for them.

<!-- Safety first: all changes go on a copy of the site, and publishing is always the owner's decision. -->

Once items are approved, follow `references/implementation.md`:

1. **Work on a copy, never the live site**: a duplicate Shopify theme, a staging site or git branch, or a draft page.
2. Implement items **one at a time**, in priority order, as small reviewable changes.
3. Use the store's **real data** for social proof, stock and prices.
4. **Verify each change** at mobile and desktop widths, and check nothing broke: add-to-cart, variant selection, cart.
5. Hand back a preview link, a change log (what changed, where, how to undo it), and a **measurement plan**: main metric (RPV), supporting metrics (add-to-cart rate, checkout starts), run for at least 2 full weeks to cover pay cycles.
6. Publishing to the live site is the owner's decision. Ask first; never publish without an explicit yes.

If you have no write access, produce a developer-ready brief for each approved item (what to change, where, acceptance criteria, how to test it) and say what access would let you do it directly.

## A note on evidence

<!-- Results quoted in the reference files come from published tests by e-commerce practitioners and research bodies. Sources are listed at the bottom of each reference file. -->

Revenue figures quoted in the reference files are self-reported by the people who ran the tests. Present them as examples of what has worked elsewhere, not as guarantees for this store.

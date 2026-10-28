# Research and benchmarks

Use these to size impact and justify priorities. Cite the source in the report.

## Cart and checkout (Baymard Institute)
- Average documented cart abandonment: **70.22%** (across 50 studies).
- Among US shoppers who abandon (excluding the ~42% "just browsing"), the reasons are:
  - extra costs too high — 40%
  - delivery too slow — 20%
  - didn't trust the site with card details — 19%
  - forced account creation — 18%
  - checkout too long or complicated — 17%
  - site errors or crashes — 17%
  - returns policy — 13%
  - couldn't see the total cost upfront — 12%
  - card declined — 10%
  - not enough payment methods — 9%
- Baymard estimates the average large site could gain **~35% in conversion rate** through better checkout design alone.
- Recommended checkout: ~7–8 form fields. Make guest checkout prominent.
- Source: https://baymard.com/lists/cart-abandonment-rate and https://baymard.com/research/checkout-usability

**Implication:** cost transparency (show the full total in the cart), delivery dates, guest checkout, trust near payment, and wallet/BNPL options are usually high-impact, low-risk fixes.

## A/B testing realities
- Most tests don't win. Agency benchmarks for e-commerce put win rates at roughly a third (e.g. one 2026 analysis of 90+ brands cites ~36%, with scarcity copy and shipping reassurance among the frequent PDP winners). Set expectations: a report is a backlog of hypotheses, not guaranteed lifts.
- Use RPV as the primary metric. Run at least 2 full weeks. Segment by device and new vs returning. Don't stop early on a peeking "win".
- Low-traffic stores (<~15k sessions/month): ship clear UX fixes (broken things, missing info, cost transparency) directly and compare before/after over equal periods. Reserve formal tests for contested changes.
- Sources: https://advertorialwizard.com/blog/ecommerce-ab-test-benchmarks-2026 · Kurt Elster (see kurt-elster.md)

## Designing for AI shopping agents (2026)
More discovery and comparison now happens through AI assistants and agents that read product data rather than looking at the page. To stay "selectable":
- Open descriptions with the facts: product type, materials, dimensions, variants. Then the story, then verifiable proof (certifications, test results).
- Replace vague adjectives with measurements.
- Complete Product schema: name, description, images, brand, SKU, GTIN, **a per-variant offer with price and live availability**, aggregateRating in server-rendered HTML, BreadcrumbList, FAQ.
- Use a consistent, flat product taxonomy and attribute:value tags. Make sure prices match between the feed/API and the page.
- Put return windows, shipping costs and delivery ranges in structured, scannable form.
- Source: https://wearepresta.com/agentic-first-shopify-designing-product-pages-for-ai-agents/

## Notes from the user's own CRO notes (Notion)
- Get products in front of customers as fast as possible. Push SEO copy below the products on collection pages.
- Readability lowers bounce (Baymard readability guidelines). Watch line length.
- Removing things often produced the best results. "Ugly" can still convert.
- Free shipping matters less than it used to (profit-dependent), but **never surprise people with extra costs at the end**.
- Recently viewed: helps returning visitors, hurts new ones (choice paralysis).
- "Frequently bought together" can lift AOV.
- Trust builders: FAQs, video testimonials, being contactable, emphasising security, third-party reviews, awards, customer logos.
- What works now may not work in 12 months — re-test winners periodically.

## Existing CRO skills (landscape, Oct 2026)
Before this skill, the public CRO skills found were **audit or recommendation only**:
- rampstackco `cro-optimization` (URL/HTML → report)
- cgallic `kai-cro` (5-layer audit → prioritised fix list)
- coreyhaines31 `marketingskills` → `cro`, `signup`, `popups` skills (MIT)
- Enrich Labs' 10 Shopify CRO skill briefs (analysis only; changes applied by a human)

What this skill adds: e-commerce-specific checklists grounded in named practitioners, an explicit approval gate, and an implementation phase that works on a copy.

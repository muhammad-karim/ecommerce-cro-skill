# Testing insights: what real split tests showed

This file is the counterweight to "best practice" lists. Audiences differ, so **test your assumptions**: confident predictions are often wrong. These are results from real Shopify split tests, paraphrased; sources are at the bottom.

## Mindset

- **Be sceptical of best practices.** Much e-commerce advice spreads because loud voices repeat it, not because of evidence. What wins on one store can lose on another.
- **Simplify.** Confusing, cluttered or slow pages leak conversions.
- **Measure revenue per visitor (RPV)**, not conversion rate alone. Track secondary goals (add-to-cart, engagement) to confirm a result is consistent.
- **Segment results** by mobile vs desktop and new vs returning visitors. They often behave differently.
- **Run tests for at least 2 weeks**, even with lots of traffic, so they cover pay cycles. A rough starting point for split testing is ~15–20k monthly visitors.
- **Talk to customers before testing.** Phone recent buyers (offer a small gift card for ~30 minutes). Run open-ended surveys and look for the phrases customers repeat. **Customers' own words make the best headlines and copy.**
- Use heatmaps, scroll maps and session recordings (Hotjar, Microsoft Clarity, Lucky Orange) to see where people get stuck, then test what you find.
- Most Shopify themes are built as catalogues, not funnels. Customising a good premium theme around the customer journey usually beats a ground-up rebuild.

## Readability (often the biggest lever)

Content and readability matter more than visual polish:
- Body text **~16px or larger**, line height **~1.5**, line length **~60–80 characters**. Don't run text full-width on big monitors.
- Dark text on a light background. Avoid low-contrast light grey.
- Break up long text. Lay out PDPs like a well-designed magazine page.
- Prefer system fonts over external web fonts where it helps Core Web Vitals.
- Tiny font-size tweaks alone didn't reach significance. Overall readability did.

## Split-test results

Use these to flag "contested" recommendations and to suggest tests:

| Test | Result | Takeaway |
|---|---|---|
| **Show prices on collection pages** (apparel) | +~23.6% RPV (97% confidence). Varied by category | Show prices. A visible price sets an expectation the PDP can meet |
| **Remove hero banner on category pages** | +16% RPV (92%) | Shoppers on a collection page already chose to shop. Get products up top |
| **Remove homepage hero slider** | Performed better | Get visitors to featured products faster |
| **Recently viewed products** | Returning visitors +~33% CR, **new visitors −~9%** | Show only to returning visitors (personalise) |
| **Add-to-cart on collection pages** | +~15% RPV (85%, borderline) | Good for cheaper, similar, multi-buy items. Weaker for high-ticket, spec-driven items. Test by category and device |
| **Breadcrumbs** | Removing them raised CR but cut multi-item orders. Keeping them gave +~53% RPV (92%) | Keep breadcrumbs. Backfill them for visitors landing from Google Shopping |
| **Free-shipping thresholds** (none vs $25 vs $75) | Checkout CR barely moved. Profit per visitor was ~$20 with no free shipping vs ~$12 at a $25 threshold (fulfilment ~$7.50/order) | Don't assume free shipping pays. Model profit. Start the threshold ~20% above AOV and test. Free shipping as a periodic promo creates natural urgency |
| **Site speed** | Matters, but its impact is often overstated. Many big stores are slow | Fix obvious problems. Don't treat speed as a silver bullet |

## Navigation and layout

- Main nav should lead straight to products and categories. Shopping links buried in dropdowns cost sales.
- Big hero banners on collection pages and PDPs push products down.
- On lead-gen pages, use one primary CTA plus at most a secondary text link.

## Case example — a watch-strap brand

They customised an existing premium theme rather than rebuilding, and walked the store as a buyer to remove friction. Customer surveys showed buyers saw the straps as a fashion accessory, not a cheap replacement, so headlines and descriptions were rewritten in customers' own words. They added a "pick your watch first" selector so shoppers only saw compatible products, plus educational landing pages for paid traffic. The redesign reportedly paid for itself within three days.

## Sources

- Ecommerce Evolution — "Split-Test Everything with Kurt Elster": https://www.omgcommerce.com/ecommerce-evolution-podcast/split-test-everything-with-kurt-elster
- Quiet Light — "Why You Should Avoid Best Practices": https://quietlight.com/podcast/why-you-should-avoid-best-practices/
- Ecommerce Evolution ep. 71 — biggest levers for conversion: https://www.omgcommerce.com/ecommerce-evolution-podcast/finding-the-biggest-levers-to-pull-for-conversion-rate-improvements
- Shopify Partners — Ethercycle / Everest Bands: https://www.shopify.com/partners/blog/19874307-partner-spotlight-ethercycle-boosts-conversions-for-everest-bands
- The Unofficial Shopify Podcast: https://podcasts.apple.com/us/podcast/id918602360

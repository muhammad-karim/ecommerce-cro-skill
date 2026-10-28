# E-commerce CRO skill for Claude

**Find out why your online store isn't selling more, then fix it.**

This is a skill for Claude. Give Claude your store's web address and it will:

1. **Look** at your store page by page, the way a shopper would (on a phone first).
2. **Report** what's stopping people from buying, with every fix ranked so the quickest, biggest wins come first.
3. **Ask** which fixes you want. Nothing changes until you choose.
4. **Build** the fixes you picked, on a copy of your site, so your live store is never touched until you're happy.

It uses the latest conversion rate optimisation (CRO) best practice and results from real e-commerce experiments.

---

## What it checks

- **Header and trust:** can shoppers instantly see why to trust you (delivery, returns, reviews)?
- **Homepage:** is it clear what you sell and where to start?
- **Menus:** can people find products quickly, especially on mobile?
- **Collection pages:** are the right products showing first, with prices and reviews?
- **Product pages:** does everything needed to buy sit at the top of the page on a phone?
- **Cart and checkout:** are there surprise costs, missing reassurance, or extra steps?
- **Landing pages for ads:** does the page match the ad and focus on one action?
- **Technical basics:** speed, readability, and product data that Google and AI shopping assistants can read.

## What you get

- **A clear report:** a short summary, a scorecard for each area of the store, and a numbered list of fixes ranked by impact and effort.
- **Honest guidance:** fixes with mixed evidence are flagged as "test this first" rather than presented as sure things.
- **Your choice:** reply "all", "quick wins only" or the numbers you want (e.g. "1, 3, 5").
- **Safe changes:** built on a duplicate theme, staging site or draft page, with a preview link, a list of exactly what changed and how to undo it, and a plan for measuring the results.
- If Claude can't edit your site directly, you get a ready-to-use brief for your developer instead.

It never invents reviews, fake stock warnings or fake "as seen in" logos.

## How to use it

**Install**
- **Claude app / claude.ai:** download this repository as a ZIP (green **Code** button › **Download ZIP**), then upload it under **Settings › Capabilities › Skills**.
- **Claude Code:** run `git clone https://github.com/muhammad-karim/ecommerce-cro-skill ~/.claude/skills/ecommerce-cro`

**Then just ask, for example:**
- "Do a CRO audit of mystore.com"
- "Why isn't my product page converting? mystore.com/products/blue-sofa"
- "Review my cart and checkout and tell me what to fix"

Works best on Shopify, WooCommerce/WordPress and custom sites. Claude does the most when it can use a browser and has access to your theme or site.

## What's in this repository

```
SKILL.md                          The instructions Claude follows (with plain-English notes)
references/
  page-checklists.md              The page-by-page checklist
  proven-page-patterns.md         Page structure that converts, common fixes, recent experiments
  testing-insights.md             What real split tests showed (including surprises)
  research-and-benchmarks.md      Checkout research and A/B testing guidance
  report-template.md              What the report looks like
  implementation.md               How changes are made safely, by platform
evals/                            Example requests used to test the skill
```

## Good to know

- Results quoted in the skill come from published tests on other stores. They're examples of what has worked, not guarantees for yours. That's why the skill treats fixes as things to test.
- Sources are listed at the bottom of each reference file.

## Licence

MIT. Free to use and adapt.

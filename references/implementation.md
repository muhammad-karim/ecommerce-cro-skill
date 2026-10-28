# Implementation playbook

Only start this once the user has approved specific items. The rules that apply on every platform:

1. **Never edit the live site directly.** Work on a duplicate theme, a staging site, a git branch or a draft page. Publishing is the owner's call, after they've previewed the changes.
2. **One recommendation = one small, reversible change.** Keep a change log as you go (item #, file or setting, before → after, how to revert).
3. **Use real data only.** Review counts, ratings, stock levels, customer numbers and press logos must come from the store or its apps. If the data doesn't exist yet, build the component to read it dynamically, or leave a clearly marked placeholder and tell the user.
4. **Verify** each change at ~390px (mobile) and desktop. Check add-to-cart, variant switching, the cart drawer and checkout entry still work. Take screenshots if you have a browser.
5. **Don't install paid apps, change payment or shipping settings, or alter prices** without explicit permission for that specific action.

## Shopify

**Access options, best first:**
- **GitHub-connected theme** (Online Store › Themes › connect a branch). Clone the repo, create a branch such as `cro/<date>`, edit, push, and preview the theme connected to that branch. Best for review and rollback.
- **Shopify CLI** (`shopify theme pull` / `shopify theme push --unpublished`), with a theme access password or staff account. Push to an **unpublished** theme and share the preview link.
- **Theme code pasted or uploaded by the user.** Edit locally and return the files plus instructions.
- **No access** → write a developer brief per item.

**Before editing:** duplicate the live theme (or push to a new unpublished theme). Identify the theme (Dawn and other OS 2.0 themes use `sections/`, `snippets/`, `templates/*.json`, `locales/`, `config/settings_schema.json`).

**Patterns:**
- Prefer **new sections or blocks with schema settings** so the owner can edit text and toggle them in the theme editor. Avoid hard-coding.
- Put copy in `locales/*.json` or section settings, not in Liquid.
- **Trust bar:** a new section in `sections/` added to header-group (OS 2.0 section groups), with icon + text blocks.
- **Free-shipping progress bar:** compute from `cart.total_price` against a threshold setting. Update it on cart change events (the theme's cart drawer JS or the `cart:updated` pattern). Use money filters to format.
- **Review stars on cards and PDP:** use the installed reviews app's snippet or metafields (`product.metafields.reviews.rating` / `rating_count` for apps that write the standard metafields). Never hard-code numbers.
- **Unit price:** Shopify supports `variant.unit_price` / `unit_price_measurement` natively. Otherwise use a variant metafield.
- **Sticky mobile ATC:** a small fixed bar shown when the main ATC scrolls out of view (IntersectionObserver). It submits the same product form and respects variant selection.
- **Estimated delivery date:** compute from settings (processing days + transit days, skipping weekends). Label it "Estimated".
- **Collection sort by RPV:** this is an admin change (collection › Sort › Manual), not code. Give the user the ordered list from their analytics, or do it via the Admin API if connected with permission.
- **Schema:** check `product` JSON-LD in `main-product` or the theme's structured-data snippet. Add per-variant offers, availability and aggregateRating where the reviews data exists.
- Run `shopify theme check` if the CLI is available.

## WordPress / WooCommerce
- Use a staging site where the host provides one. Otherwise edit a child theme, or use block patterns and draft pages.
- On WordPress.com, the WordPress MCP connector can create draft pages and edit content. Keep changes as drafts and share the preview links.
- WooCommerce hooks for PDP inserts: `woocommerce_single_product_summary` (with priorities), `woocommerce_after_add_to_cart_button` for trust/review cards under the ATC, and `woocommerce_before_cart` / `woocommerce_cart_totals_after_order_total` for cart messaging.
- Prefer a small custom plugin or child-theme `functions.php` over editing the parent theme.

## Custom / static / headless sites (code repo)
- Clone the repo, create a branch, and make the changes as small commits (one per recommendation, with the item # in the commit message).
- Run the project's build and tests, and preview locally if possible.
- Open a pull request with a summary table of the changes and screenshots. Don't merge without the owner's approval.

## Landing page builders (Replo, Shogun, PageFly, GemPages, Unbounce, etc.)
- Duplicate the page and edit the duplicate. If there's no API or connector, give step-by-step build instructions per item instead.

## Developer brief format (when you can't implement)
For each approved item:
- **Goal / hypothesis**
- **Where** (template, section)
- **Spec** (copy, layout, behaviour on mobile and desktop, data sources)
- **Acceptance criteria** (testable bullets)
- **QA steps** (devices, variants, empty cart, sold-out product)
- **Rollback**

## Handover
End with:
1. A preview link (unpublished theme, staging URL or PR).
2. A change log table: # · change · files/settings · how to revert.
3. A measurement plan: RPV as primary, secondary metrics, test or before/after, duration ≥2 weeks, and the date to review.
4. A question: publish now, run as an A/B test, or hold?

# ecommerce-cro — a Claude skill for CRO audits and implementation

A Claude skill that **audits an e-commerce site**, writes a **prioritised CRO report**, asks **which recommendations to implement** (all, some, or none), and then **implements the approved changes** safely, on a duplicate theme, staging site or branch, never the live site.

## What makes it different
Most public CRO skills stop at a report. This one:
- Uses e-commerce-specific, page-by-page checklists (header, homepage, mega menu, collections, PDP, cart, checkout, landing pages, post-purchase, technical/schema).
- Is grounded in named practitioners:
  - **Oliver Kenyon (ConversionWise)**: the ATIDFA framework (Attention, Transformation, Interest, Desire, FAQ, Action), above-the-fold rules, recurring fixes from his 100 redesigns, and his 2026 test wins.
  - **Kurt Elster (Ethercycle)**: a test-first mindset, readability rules, RPV over conversion rate, and split-test results that contradict common "best practice".
  - **Baymard Institute**: cart and checkout abandonment research.
  - Readiness for AI shopping agents (structured data, measurable specs).
- Has an explicit approval gate before any change.
- Includes implementation playbooks for Shopify (GitHub-connected themes / CLI, OS 2.0 sections), WooCommerce, code repos and page builders, or developer briefs when there's no access.
- Refuses fake urgency and fake social proof.

## Structure
```
ecommerce-cro/
├── SKILL.md                         # workflow: scope → evaluate → report → approve → implement
├── references/
│   ├── page-checklists.md           # the core audit checklist
│   ├── oliver-kenyon.md             # ATIDFA, redesign patterns, recent tests
│   ├── kurt-elster.md               # test results, readability, research methods
│   ├── research-and-benchmarks.md   # Baymard, A/B realities, AI agents, CRO notes
│   ├── report-template.md           # report format + ICE scoring
│   └── implementation.md            # platform playbooks + safety rules
└── evals/                           # test prompts (claude plugin eval format)
```

## Install
- **Claude.ai / Claude app:** upload the `.skill` file (or zip this folder) under Settings › Capabilities › Skills.
- **Claude Code:** copy the folder to `~/.claude/skills/ecommerce-cro/`.

Then just ask, e.g. *"Do a CRO audit of mystore.com and tell me what to fix on the product page."*

## Credits
The principles are paraphrased from public material by Oliver Kenyon, Kurt Elster and Baymard Institute, with links in each reference file. This skill isn't affiliated with or endorsed by them. Revenue figures are as self-reported by the practitioners and are examples, not guarantees.

## Licence
MIT

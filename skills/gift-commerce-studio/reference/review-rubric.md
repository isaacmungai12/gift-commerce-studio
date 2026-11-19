# Review Rubric

Use for every independent review. The reviewer is a fresh sub-agent or session that has not seen the builder's reasoning. Give it the live URL (or screenshots at 375px, 768px and 1440px), the brief and this file.

Score each criterion 0-10. Give the evidence (screenshot, measurement or quoted element) for every score and the specific fix for any score below 10.

**Pass bar: every criterion 9 or more.** Any criterion below 9 is fixed and re-scored by a fresh reviewer. An average does not pass; the lowest score decides.

## Criteria

| # | Criterion | What a 9-10 looks like | Common reasons for lower scores |
|---|---|---|---|
| 1 | **First-screen clarity** | Within 5 seconds on a phone: what they sell, for which occasions, delivery promise, one clear action. | Slogan without product, carousel, no delivery info, two competing CTAs. |
| 2 | **Desirability of product presentation** | Real, consistent, beautiful photos; you want the box. "What's inside" is obvious. Second image on cards. | Stock or AI-looking images, inconsistent crops and light, contents unclear. |
| 3 | **Ease of finding a gift** | Any product reachable in 2 clicks by occasion, recipient or budget; filters and gift finder work. | Only "Shop all", no budget bands, deep menus, dead filters. |
| 4 | **Gift-flow completeness** | Gift message (with preview), delivery date, delivery or pickup, recipient details clearly labelled, hide-price option, all before payment. | Gift options only at checkout, "Name/Address" ambiguity, no date picker. |
| 5 | **Trust** | Named guarantees, real reviews or customer photos, payment methods, delivery areas, human contact, all near the top and by Add to Cart. | Generic claims, fabricated or missing proof, contact buried in footer. |
| 6 | **Motion quality** | One authored moment that feels intentional and fast; transitions under ~400ms; nothing janky; `prefers-reduced-motion` fully respected. | Motion everywhere, scroll-jacking, layout shift, ignored reduced-motion. |
| 7 | **Typography and craft** | Passes Impeccable's `reference/craft-floor.md`: type scale, measure, rhythm, spacing, colour contrast, no AI-slop tells. | Default fonts, cramped padding, inconsistent radii, gradient clichés. |
| 8 | **Mobile** | Designed for 375px first; thumb-reachable CTA; tap targets 24px minimum (44px preferred); no horizontal scroll; sticky add-to-cart where useful. | Desktop squeezed down, tiny targets, overflowing tables, hidden cart. |
| 9 | **Performance** | Lighthouse mobile performance 90 or more; LCP under 2.5s; CLS under 0.1; INP under 200ms; images responsive and modern formats. | Huge hero images, blocking fonts or scripts, heavy animation libraries on load. |
| 10 | **Accessibility** | WCAG 2.2 AA: contrast, focus visible and not obscured, keyboard paths, labels, alt text, target size, no motion traps. | Missing labels, low contrast text on photos, focus lost in dialogs. |

## Report format

```
Overall: PASS / FAIL (lowest score: N on criterion X)

| # | Criterion | Score | Evidence | Fix |
|---|---|---|---|---|
...

Top 3 changes that would most lift sales:
1. ...

Final question: Would a discerning client pay a premium agency price for this? What's missing?
Answer: ...
```

The final question is mandatory. If the honest answer is "not yet", list what is missing and treat it as a fail even if every number is 9 or more.

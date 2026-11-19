---
name: gift-commerce-studio
description: "Use to design, build, critique or audit premium gifting and boutique e-commerce sites (gift boxes, hampers, flowers, curated packages) and other high-converting sales sites: homepages, product and category pages, box builders, gift flows, WhatsApp or cart checkout, and independent design reviews. Builds on Impeccable and adds a gifting playbook, photo direction, conversion checklist, review rubric and stack."
version: 0.1.0
user-invocable: true
argument-hint: "[build · critique · audit · review · photos · checkout] [target]"
license: Apache 2.0
---

# Gift Commerce Studio

Make sites that look like a premium agency built them and that sell gifts. First client: Gift & Moments, a Kenyan gift-package business. The bar is "a discerning client would pay a premium agency price for this", proven by the rubric, not by opinion.

This skill sits on top of Impeccable. Impeccable owns general craft (typography, layout, colour, motion, anti-slop). This skill owns what gifting commerce needs on top of that.

## Load order (every session)

1. Load the Impeccable skill at `~/.claude/skills/impeccable/SKILL.md` and follow its setup and routing.
2. Read `~/.claude/skills/impeccable/reference/craft-floor.md` immediately before any UI edit, however small.
3. Load the references below that the task needs:
   - [reference/gifting-playbook.md](reference/gifting-playbook.md): patterns, award-level interactions, category architecture, benchmarks. Always for build and critique.
   - [reference/conversion-checklist.md](reference/conversion-checklist.md): gift flow, delivery promise, add-ons, reminders, WhatsApp checkout. Always for product, cart and checkout work.
   - [reference/photo-direction.md](reference/photo-direction.md): any task that chooses, sources, briefs or places images.
   - [reference/review-rubric.md](reference/review-rubric.md): every critique, audit or sign-off.
   - [reference/stack.md](reference/stack.md): any build, motion or performance task.

If Impeccable's CLI (`scripts/impeccable ...`) is ever run, prefix it with `DO_NOT_TRACK=1` so its anonymous telemetry stays off. Do not install Impeccable hooks unless Isaac asks.

## Non-negotiables

- **Real, not fabricated.** Never invent reviews, testimonials, ratings, order counts, press logos, awards or customer names. Use placeholders marked `TODO: real quote from client` until the client supplies the real thing.
- **Real photography over AI imagery** for products, packaging, hands and people. AI images only for abstract texture, never presented as the product.
- **Every claim is true.** Delivery cut-offs, delivery areas, prices, guarantees and stock come from the client. If unknown, ask once and leave a visible TODO; never guess a time or price.
- **Prices in the client's currency** (Gift & Moments: KES, written `KES 4,500`), with "from" prices where options vary.
- **Mobile first.** Most gift buyers in Kenya arrive on a phone from Instagram, TikTok or WhatsApp. Design and verify at 375px before desktop.
- **One authored motion moment per page**, not motion everywhere. Respect `prefers-reduced-motion` everywhere.
- **Credit every third-party asset** in the project's image MANIFEST.

## Workflow: build or redesign

1. **Brief.** Confirm the client's occasions, products, price bands, delivery areas and cut-off times, pickup option, payment method (M-Pesa, card, WhatsApp order) and brand assets. Record gaps as TODOs; do not stall on them.
2. **Architecture.** Lay out navigation from the category architecture in the playbook. Every product reachable in two clicks by occasion, recipient or budget.
3. **First screen.** Occasion tiles, delivery promise with cut-off, one clear call to action, trust line near the top. No hero carousel.
4. **Product page.** Gallery of real photos (what's inside, unboxing, in hands), from-price, options, free gift message with live preview, delivery date picker, 2-3 "arrives together" add-ons, named guarantee.
5. **Gift flow and checkout.** Run the conversion checklist line by line. For WhatsApp-first markets, build the composed wa.me order message.
6. **Motion.** Pick one award-level interaction from the playbook that fits the brand and budget. Build it properly (see stack.md), with a reduced-motion fallback.
7. **Verify.** Look at the rendered pages at 375px, 768px and 1440px. Run Lighthouse mobile and an accessibility pass. Fix before showing anyone.
8. **Independent review.** Score with the rubric (see below). Iterate until it passes.

## Workflow: critique or audit an existing site

1. Load the Impeccable `critique` or `audit` playbook as usual.
2. Add a pass against the 10 gifting patterns: mark each present, weak or missing, with a screenshot reference.
3. Run the conversion checklist; quote the evidence for each fail.
4. Score with the review rubric. Lead the report with the three changes that would most lift sales, then the craft fixes.

## Independent review

- Run the review in a separate sub-agent (or a fresh session) that has not seen your reasoning. Give it the live URL or screenshots, the rubric file path and the brief, not your conclusions.
- Pass bar: every one of the 10 criteria scores 9 or more. Anything below 9 gets fixed and re-scored by a fresh reviewer.
- End every review with: "Would a discerning client pay a premium agency price for this? What's missing?" and act on the answer.

## Companion skills

Cloned under `~/.claude/skills-src/` for reference; load the relevant file when the task needs it:

- `emilkowalski_skill`: animate, review-animations (motion feel and timing).
- `greensock_gsap-skills`: GSAP and ScrollTrigger usage.
- `remotion-dev_skills`: product videos and animated social assets.
- `coreyhaines31_marketingskills`: cro, copywriting.
- `vercel-labs_agent-skills`: web-design-guidelines.
- `addyosmani_web-quality-skills`: web-quality-audit, accessibility, performance.

## Done means

- All 10 gifting patterns present or consciously excluded with a reason.
- Conversion checklist passes, or each fail is a client-owned TODO.
- Image MANIFEST complete with credits and licences.
- Lighthouse mobile performance 90 or more, LCP under 2.5s, WCAG 2.2 AA.
- Independent rubric review: every criterion 9 or more.

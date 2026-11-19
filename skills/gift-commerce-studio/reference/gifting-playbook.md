# Gifting Playbook

What the best gifting sites do consistently, the interactions that lift a site to award level, and how to structure the catalogue. Use it to build, and as a checklist when critiquing.

## The 10 consistent patterns

Top gifting sites repeat these. Treat each as default-on; leave one out only with a stated reason.

1. **Occasion tiles on the first screen.** Birthday, Anniversary, Thank You, Get Well, New Baby, Sympathy, Corporate, "Just Because". Large, photographic, tappable, above the fold on mobile. The shopper arrives with an occasion, not a SKU.
2. **Visible delivery promise and cut-off.** "Order by 2pm for same-day delivery in Nairobi" in the header bar or hero, repeated on the product page and in the cart. It must be accurate and update with the clock (see conversion-checklist.md).
3. **Several ways in.** By occasion, by recipient (For Her, For Him, For Mum, For Colleagues, For Kids), by type (hampers, flowers, cakes, keepsakes), and by three price bands (e.g. Under KES 3,000 / KES 3,000-7,000 / KES 7,000+). Each is one tap from the homepage.
4. **Product cards that sell.** One badge max (Bestseller, New, Same-day), product name, "from" price, and a second image on hover (desktop) or swipe (mobile) showing what's inside or the unboxing. No star ratings unless they are real.
5. **"Arrives together" add-ons on the product page.** Two or three small extras (card, balloon, chocolates, candle) as one-tap checkboxes with thumbnail and price, before Add to Cart. Not a carousel of 12.
6. **Free gift message on the product page with live preview.** A text area with character count, rendered live on a card mock-up as the shopper types. Say "Free" next to it.
7. **Occasion reminders.** "Remind me next year" after purchase and a simple reminder sign-up (name, occasion, date) that feeds email or WhatsApp. Reminders are a large share of repeat revenue for florists.
8. **Subscriptions or clubs.** Monthly flowers, quarterly treat box, or a corporate gifting programme. Even a "talk to us about regular gifting" block counts at launch.
9. **Named guarantees.** Specific, ownable promises: "We send you a photo before dispatch", "Fresh for 7 days or we replace it", "Delivered on the day you choose". Name them; generic "quality guaranteed" does nothing.
10. **Trust near the top.** Delivery areas, payment methods (M-Pesa logo, cards), real review count or real customer photos, and how to reach a human (WhatsApp) within the first two screens.

## The 5 award-level interactions

Pick one per site as the authored moment, at most two. Each needs a reduced-motion path that keeps the function.

1. **Live box builder.** Shopper picks a box, then items drop into it visually with a running total and a "box is full" state. Items animate into slots; the box can be rotated or opened. Reduced motion: items appear in place with a fade.
2. **Live gift-note preview in a handwriting font.** The message renders on a card in a self-hosted handwriting face as it is typed, with a subtle paper texture and the sender's name. Reduced motion: same preview, no write-on effect.
3. **Shared-element page transitions.** The product image on the card morphs into the product page hero (Astro View Transitions with `transition:name`). Reduced motion: instant swap or cross-fade.
4. **Skippable first-visit unwrap intro.** A short (under 2s) ribbon-pull or lid-lift reveal on first visit only, with a visible Skip, remembered in storage, never blocking LCP content. Reduced motion: skipped entirely.
5. **Pre-dispatch photo.** After ordering, the customer receives a photo of their actual gift before it leaves (WhatsApp or email), and the site shows this promise with real example photos. It is an operations feature that reads as luxury.

## Category architecture

Primary navigation:

- **Occasions**: Birthday, Anniversary, Love & Romance, Thank You, Congratulations, New Baby, Get Well, Sympathy, Corporate, Just Because, seasonal (Valentine's, Mother's Day, Christmas, Eid, Diwali as relevant).
- **For Them**: Her, Him, Mum, Dad, Couples, Friends, Colleagues, Kids, Teachers.
- **By Budget**: three bands that match the client's price spread.
- **Build a Box**: the box builder or a curated "choose 3-5 items" flow.
- **Little Extras**: cards, balloons, chocolates, candles, teddies; also surfaced as add-ons.
- **Our Story**: the makers, where they are, how gifts are packed, the guarantees, real photos of the team and space.

Sentiment tags (filterable, shown as small chips): Thoughtful, Indulgent, Celebration, Comfort, Romantic, Fun, Luxe, Practical. Tag every product with one to three.

Keep top-level items to six. Mobile menu shows Occasions expanded by default.

## Benchmarks

Compare work against these, studying the named strength rather than copying the look:

| Site | Study it for |
|---|---|
| Bloom & Wild | Letterbox format story, gift flow, reminders, clean product pages |
| Fig & Bloom | Premium editorial photography, delivery promise clarity |
| Edible Blooms | Occasion and recipient navigation, add-ons, cut-off messaging |
| Venus et Fleur | Luxury restraint, product as object, personalisation |
| BOXFOX | Build-a-box flow, box curation, corporate gifting |
| UrbanStems | Add-ons on the product page, subscription, delivery-date picker |
| Ladurée | Brand world, packaging as hero, colour discipline |
| Amoroses (Awwwards Honourable Mention) | Motion, transitions, award-level craft on a flower shop |
| Flower Dose | Subscriptions, warm photography, simple choices |

When critiquing, name which benchmark does a given pattern best and what the gap is.

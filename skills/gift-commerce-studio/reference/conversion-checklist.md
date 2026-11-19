# Conversion Checklist

Run this line by line on every product, cart and checkout build. Mark each item Pass, Fail (with evidence) or Client TODO. Figures below are from published research and case studies; treat single-company cases as directional, not guarantees.

## 1. Gift flow (Baymard)

Baymard's gifting research found about 80% of e-commerce sites hide gift options until checkout, so shoppers cannot tell whether a gift is possible while they decide.

- [ ] "This is a gift" is visible on the product page, not only at checkout.
- [ ] Free gift message field on the product page, with character limit, count and live preview.
- [ ] Option to hide prices on the packing slip / receipt ("Hide price from recipient").
- [ ] Address fields labelled for the recipient: "Recipient's name", "Recipient's phone", "Recipient's address", not a bare "Name" / "Address" that buyers confuse with their own.
- [ ] Buyer's details and recipient's details are clearly separate sections.
- [ ] Delivery date picker on the product page or cart, with unavailable dates disabled and the reason shown.
- [ ] Delivery or pickup choice, with pickup location and hours stated.
- [ ] Surprise option: "Don't call the recipient before delivery" or "Call the recipient to arrange" choice.
- [ ] Order summary repeats message, date, recipient and add-ons before payment.

## 2. Delivery promise and cut-off clock

- [ ] Delivery promise in the header bar or hero, on the product page and in the cart.
- [ ] Live cut-off countdown ("Order in 2h 14m for same-day delivery in Nairobi"). One florist case reported about a 27% lift from adding a cut-off clock.
- [ ] The clock is accurate: uses the client's timezone (Africa/Nairobi for Gift & Moments), switches to "next-day" after the cut-off, respects closed days and holidays, and matches what operations can actually deliver. A wrong clock is a broken promise; if the true cut-off is unknown, do not ship a clock.
- [ ] Delivery areas and fees stated before checkout.

## 3. Add-ons

- [ ] Two or three "arrives together" add-ons on the product page, before Add to Cart. UrbanStems moved add-ons from checkout to the product page and reported better attach rates; shoppers decide extras while they are choosing the gift, not while paying.
- [ ] Add-ons are one tap, show thumbnail and price, and update the total live.
- [ ] No pre-ticked paid add-ons.

## 4. Reminders and repeat

- [ ] "Remind me next year" offer on the confirmation page.
- [ ] Reminder sign-up (name, occasion, date, channel: email or WhatsApp).
- [ ] Reminders are reported to drive around 40% of email revenue for some florists; build the capture even if the sending is manual at first.
- [ ] Subscription / club or corporate gifting entry point.

## 5. Gift finder

- [ ] A short gift finder or quiz (occasion, recipient, budget, vibe; three or four steps) that ends in a filtered product list. Published gift-quiz case studies show lifts in conversion and order value; treat them as directional and measure your own.
- [ ] Skippable, works without JavaScript falling back to filter links.

## 6. Trust and social proof

- [ ] Real customer photos gallery or per-product real photos (with permission). Customer-photo content consistently gets higher engagement than studio imagery.
- [ ] Real review count and source, or no reviews section at all. Never fabricated.
- [ ] Named guarantees near the Add to Cart button.
- [ ] Payment methods (M-Pesa, cards) and a WhatsApp contact visible before checkout.

## 7. WhatsApp checkout (Kenya and similar markets)

Many Kenyan buyers prefer to confirm orders on WhatsApp and pay by M-Pesa. Build the cart so "Order on WhatsApp" composes a neat, complete message and opens `https://wa.me/<number>?text=<encoded>`.

- [ ] Number in international format without `+` or spaces (e.g. `2547XXXXXXXX`), stored in one config value.
- [ ] Message built from cart state, URL-encoded with `encodeURIComponent`, kept under roughly 2,000 characters.
- [ ] Message contains, in this order:

```
Hello Gift & Moments, I'd like to place an order.

Order ref: GM-20261119-4821
Items:
- Classic Celebration Box x1 - KES 6,500
- Add-on: Handwritten card x1 - KES 300

Gift message: "Happy birthday, Wanjiru! Love, Achieng"
Recipient: Wanjiru K., 07XX XXX XXX
Delivery: Delivery to Kilimani, Nairobi
Date: Sat 22 Nov 2026
Notes: Please don't call before delivery (surprise)

Subtotal: KES 6,800
Delivery: KES 400
Total: KES 7,200
Deposit to confirm (50%): KES 3,600
```

- [ ] Order ref is unique per order (date + short random), shown to the buyer on the site too.
- [ ] Pickup orders show pickup location and time instead of address and delivery fee.
- [ ] Deposit amount and rule come from the client; if unknown, omit the deposit line and leave a TODO.
- [ ] Buyer's own phone number is not put in any URL other than the wa.me message they send themselves.
- [ ] A confirmation screen after the tap says what happens next ("We'll reply on WhatsApp within 30 minutes with M-Pesa details").
- [ ] Tested on a real phone: message opens in WhatsApp with line breaks and characters intact.

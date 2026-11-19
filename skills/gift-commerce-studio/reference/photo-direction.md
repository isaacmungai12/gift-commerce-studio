# Photo Direction

Photography decides whether a gifting site looks premium. Real beats generated: Baymard's 2026 research found about 60% of shoppers feel less confident buying when product images look AI-generated. Shoppers buying a gift need to trust that the box that arrives is the box they saw.

## The look

- **Side-window daylight.** Soft natural light from one side, gentle shadows, no flash, no hard studio white unless it is a deliberate catalogue grid. Morning or late-afternoon warmth.
- **Real hands.** Hands tying the ribbon, lifting the lid, holding the card. Varied skin tones that reflect the actual customer base (for Gift & Moments, Kenyan customers). Clean, natural nails; no stock-model perfection.
- **Unboxing sequence.** Three to five frames per hero product: closed box with ribbon, lid lifting, contents revealed, card in hand, recipient's reaction (only with real consent).
- **Lived-in props.** A wooden table, linen, a coffee cup, a plant, a window ledge. Props suggest a home, never compete with the product. Avoid fake marble and generic flat white.
- **"What's inside" flat lay.** One overhead shot per product with every item laid out and labelled in the copy. This is the image that answers "what do I get for the money".
- **Customer photos.** Real photos sent by customers (with permission), shown in a gallery or on product pages. They outperform polished imagery for trust.
- **Consistency.** Same light direction, colour temperature and crop ratios across the catalogue (e.g. 4:5 for cards, 1:1 for flat lays). Edit as a set.

## Sourcing

Priority order:

1. **Client's own photos.** Brief the client with a shot list (above) and phone tips: daylight near a window, turn off flash, wipe the lens, shoot the same angles for every product. A good phone in good light beats a mediocre studio.
2. **Free licensed real photos** for mood, backgrounds and category tiles only, never presented as the client's product:
   - **Unsplash** (Unsplash License): free for commercial use, no attribution required but credit anyway in the MANIFEST. Not for selling the photo unaltered or building a competing service.
   - **Pexels** (Pexels License): free for commercial use, attribution appreciated. Do not imply endorsement by people pictured; do not sell unaltered copies.
   Prefer photos showing African people and settings where people appear; search terms like "Nairobi", "Kenyan", "African woman gift", "hands ribbon".
3. **AI imagery**: only abstract textures or backgrounds, never products, people or packaging shown as real.

## MANIFEST

Keep `src/assets/images/MANIFEST.md` (or the project's equivalent) with one row per image:

| File | Source | Author | Licence | Original URL | Used on | Notes |
|---|---|---|---|---|---|---|
| hero-birthday.jpg | Unsplash | Jane Doe | Unsplash License | https://unsplash.com/photos/... | Home, occasion tile | Cropped 4:5 |
| box-classic-inside.jpg | Client | Gift & Moments | Owned | - | Product: Classic Box | Shot 2026-11 |

Rules:

- Every image in the build has a row. Missing row = not shippable.
- Client images say "Client / Owned".
- Replace stock with client photos as they arrive; keep the row history.

## Never fabricate

- No invented reviews, testimonials, star ratings, customer names, customer photos, "as seen in" logos, order counts or awards.
- No AI-generated "customer" faces or "happy recipient" photos.
- Until real reviews exist, use a placeholder block marked `TODO: real customer quote` or leave the section out. An empty slot is better than a fake one.

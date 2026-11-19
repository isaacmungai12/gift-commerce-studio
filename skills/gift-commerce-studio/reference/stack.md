# Stack

The default stack, as used for Gift & Moments. Change it only for a reason the client gives (existing Shopify store, CMS requirement, etc.).

| Layer | Choice | Why |
|---|---|---|
| Site | **Astro** (static output) | Fast by default, ships little JS, easy content collections for products. |
| Page transitions | **Astro View Transitions** (`<ClientRouter />`, `transition:name`) | Shared-element morphs from product card to product page with native fallback. |
| Animation | **GSAP + ScrollTrigger** | Reliable, well-documented, free (including plugins). |
| Smooth scroll | **Lenis** (`lenis` package) | Light, plays well with ScrollTrigger when wired as below. |
| Fonts | **@fontsource** self-hosted packages | No third-party font requests, `font-display: swap`, subset weights only. |
| Deploy | **Netlify** | Simple static deploys, preview URLs per branch, forms if needed. |

Performance budget: Lighthouse mobile 90 or more, LCP under 2.5s, CLS under 0.1. Load GSAP and Lenis only on pages that use them, after first paint.

## Shared-element transitions

- Give the card image and the product hero the same `transition:name={`product-${slug}`}`. Names must be unique per page.
- Keep transition durations short (250-400ms). Let the browser's reduced-motion handling apply; Astro respects `prefers-reduced-motion` for its built-in animations, and custom ones must check it too.
- Re-run page scripts on `astro:page-load`, not `DOMContentLoaded`, because client-side navigation does not fire the latter.

## Lenis with GSAP and Astro (in-house rules)

Lenis goes wrong when it is created twice, runs its own RAF loop alongside GSAP's, or survives a page swap. Follow these rules exactly:

1. **Respect reduced motion first.** If `matchMedia('(prefers-reduced-motion: reduce)').matches`, do not create Lenis at all. Native scrolling is the reduced-motion experience.
2. **Init once per page view.** Keep one module-level `lenis` variable. Never create a second instance while one exists.
3. **Drive Lenis from GSAP's ticker**, not its own loop: create it with `autoRaf: false` (the default) and add `gsap.ticker.add(t => lenis.raf(t * 1000))`. GSAP's time is seconds; Lenis wants milliseconds.
4. **Keep ScrollTrigger in sync:** `lenis.on('scroll', ScrollTrigger.update)`.
5. **Turn off lag smoothing:** `gsap.ticker.lagSmoothing(0)` so scroll and animation never drift after a dropped frame.
6. **Destroy on `astro:before-swap`, recreate on `astro:page-load`.** Remove the ticker callback, destroy Lenis, kill ScrollTriggers, then rebuild on the new page.
7. Import Lenis's stylesheet (`lenis/dist/lenis.css`) so `html.lenis` rules apply.

```js
// src/scripts/smooth-scroll.js
import Lenis from 'lenis';
import 'lenis/dist/lenis.css';
import { gsap } from 'gsap';
import { ScrollTrigger } from 'gsap/ScrollTrigger';

gsap.registerPlugin(ScrollTrigger);

let lenis = null;
const tick = (time) => lenis?.raf(time * 1000);

function init() {
  if (lenis) return;                                   // once
  if (matchMedia('(prefers-reduced-motion: reduce)').matches) return;
  lenis = new Lenis();                                 // autoRaf defaults to false
  lenis.on('scroll', ScrollTrigger.update);
  gsap.ticker.add(tick);
  gsap.ticker.lagSmoothing(0);
}

function destroy() {
  gsap.ticker.remove(tick);
  ScrollTrigger.getAll().forEach((st) => st.kill());
  lenis?.destroy();
  lenis = null;
}

document.addEventListener('astro:page-load', init);    // fires on first load and after each navigation
document.addEventListener('astro:before-swap', destroy);
```

Also: anchor links should call `lenis.scrollTo(target)`; dialogs and the mobile menu should call `lenis.stop()` on open and `lenis.start()` on close; set `data-lenis-prevent` on inner scrollable areas (cart drawer, long dropdowns).

## Fonts

- Install only the weights used: `npm i @fontsource/<display-face> @fontsource-variable/<text-face>`.
- Import in the base layout; preload the one weight used above the fold.
- A handwriting face for the gift-note preview (self-hosted, loaded only on the product page).

## Companion skills

Cloned in `~/.claude/skills-src/`. Read the relevant SKILL.md when the task needs it:

| Need | Path |
|---|---|
| Motion feel, timing, review | `emilkowalski_skill/skills/animate/`, `emilkowalski_skill/skills/review-animations/` |
| GSAP and ScrollTrigger | `greensock_gsap-skills/skills/gsap-core/`, `gsap-scrolltrigger/`, `gsap-performance/`, `gsap-frameworks/` |
| Product and social videos | `remotion-dev_skills/skills/remotion-best-practices/`, `remotion-create/` |
| Conversion and copy | `coreyhaines31_marketingskills/skills/cro/`, `coreyhaines31_marketingskills/skills/copywriting/` |
| Design guidelines check | `vercel-labs_agent-skills/skills/web-design-guidelines/` |
| Quality, accessibility, performance | `addyosmani_web-quality-skills/skills/web-quality-audit/`, `accessibility/`, `performance/`, `core-web-vitals/` |

These are reference copies, not installed skills. Read them; do not run their install scripts without asking Isaac.

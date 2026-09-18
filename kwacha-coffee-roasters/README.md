# Kwacha Coffee Roasters — Website Project

WEDE5020 Portfolio of Evidence. A small-business website for Kwacha Coffee
Roasters, an independent Johannesburg specialty coffee roastery.

## Pages

- `index.html` — Home
- `about.html` — About Us
- `products.html` — Our Roasts
- `contact.html` — Contact / Enquiry
- `faq.html` — FAQ

## Tech Stack

- HTML5
- CSS3 (mobile-first, responsive, CSS animations)
- Vanilla JavaScript (added in Part 3, for the FAQ accordion)

## Design notes

The name "Kwacha" is a Bemba/Nyanja word meaning "it is dawn," and is also
the currency of Zambia and Malawi — two of the roastery's sourcing
countries. That double meaning drives the visual identity:

- **Colour** — roasted-bean charcoal (`#1C1712`), burnt copper (`#B4592B`)
  and dawn gold (`#C0973C`) on a warm stone paper background (`#E7E1D2`),
  rather than a generic light-cream-and-terracotta palette.
- **Type** — Fraunces (display, used for headings and italic accents) paired
  with Work Sans (body).
- **Recurring device** — an 8px "horizon band" gradient strip runs under the
  header on every page; the home page hero expands it into a small SVG
  illustration of the sun rising over layered highveld hills, standing in
  for photography until real roastery shots are available.
- **Layout** — the roast process on the home page is the only numbered
  sequence, since it's the only content that's actually sequential. Product
  and origin listings use editorial rows rather than a repeated card grid,
  and the FAQ page uses native `<details>`/`<summary>` accordions.
- **Motion** — kept deliberately narrow rather than scattered across every
  section. There's one orchestrated moment (the home hero plays an actual
  sunrise on load: the sun lifts into place, a glow blooms once, then the
  highveld ridgelines settle in after it) and one recurring cue (a single
  light sweeps the horizon band once per page load, echoing the same
  dawn-breaking idea on every page without repeating the full hero
  sequence). Everything else only moves in response to what someone does:
  the nav underline, the button press state, and the FAQ accordion, which
  now opens and closes with an animated height transition in `js/script.js`
  instead of snapping instantly. All of it is switched off automatically
  for anyone with `prefers-reduced-motion: reduce` set.

## Changelog

### Part 1
- Initial HTML file structure created (5 pages).
- Consistent header, navigation, and footer across all pages.

### Part 2
- Linked Google Fonts (Fraunces for headings, Work Sans for body text).
- Added CSS reset and base styles (colour scheme, box-sizing, base
  typography).
- Styled header/navigation using Flexbox, with a dark header and a
  horizon-gradient band as a recurring brand device.
- Built the home hero with Flexbox and an inline SVG dawn illustration in
  place of a stock photo.
- Rewrote copy across all five pages with specific, roastery-grounded
  content (sourcing countries, roast process, team roles) instead of
  placeholder text.
- Replaced the repeated card-grid pattern with an editorial row list
  (home, products) and a numbered sequence only where the content is
  genuinely sequential (roast process).
- Converted the FAQ page to a native accordion using `<details>`/`<summary>`.
- Styled the enquiry form with underline inputs instead of boxed fields.
- Added responsive breakpoints at 768px (tablet) and 480px (mobile).

### Part 3
- Turned the home hero SVG into a single orchestrated on-load animation:
  the sun rises (`@keyframes rise`), a soft gold glow blooms behind it once
  as it settles (`@keyframes glow-bloom`), then the two hill layers rise
  into frame after it (`@keyframes hill-rise`) — a sunrise happening in
  the order a real one would, not several effects firing at once.
- Animated the horizon band with a single light sweep on load
  (`@keyframes dawn-sweep`) so the recurring brand device gets its own
  small version of the same dawn-breaking motion on every page.
- Replaced the nav's static active-page border with an animated underline
  (`transform: scaleX()`) that responds to hover, focus and the active
  page, and added a small press-state (`:active { transform: scale() }`)
  to both button styles.
- Added `js/script.js`: intercepts clicks on each FAQ `<summary>` and
  animates the answer open/closed by transitioning `max-height` on a new
  `.faq-body` wrapper, instead of the instant show/hide native `<details>`
  gives by default. Checks `prefers-reduced-motion` and skips straight to
  the end state if it's set.
- Confirmed the global `prefers-reduced-motion: reduce` rule in
  `style.css` (added in Part 2) still catches all of the above — every
  `animation` and `transition` on the page collapses to effectively 0ms
  for anyone who has that preference set at the OS level.
- _Next: replace the SVG hero placeholder with real photography, then test
  and capture screenshot evidence at desktop/tablet/mobile widths for this
  README._

## References

American Heritage Dictionary (2022) *Kwacha*. 5th edn. Boston: HarperCollins
Publishers. Available at: https://www.ahdictionary.com/word/search.html?q=kwacha
(Accessed: 18 September 2026).

Google Fonts (no date) *Fraunces*. Available at:
https://fonts.google.com/specimen/Fraunces/about (Accessed: 18 September
2026).

Google Fonts (no date) *Work Sans*. Available at:
https://fonts.google.com/specimen/Work+Sans/about (Accessed: 18 September
2026).

Merriam-Webster (no date) *Kwacha*. Available at:
https://www.merriam-webster.com/dictionary/kwacha (Accessed: 18 September
2026).

Mozilla Developer Network (no date) *&lt;details&gt;: The Details disclosure
element*. Available at:
https://developer.mozilla.org/en-US/docs/Web/HTML/Element/details (Accessed:
18 September 2026).

Mozilla Developer Network (no date) *CSS animations*. Available at:
https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_animations (Accessed:
18 September 2026).

Mozilla Developer Network (no date) *prefers-reduced-motion*. Available at:
https://developer.mozilla.org/en-US/docs/Web/CSS/@media/prefers-reduced-motion
(Accessed: 18 September 2026).

South African History Online (2013) *28 August 1970 — Malawi replaces the
Malawian pound with the Kwacha*. Available at:
https://sahistory.org.za/node/96343 (Accessed: 18 September 2026).

W3C Web Accessibility Initiative (2023) *Understanding Success Criterion
2.3.3: Animation from Interactions*. Available at:
https://www.w3.org/WAI/WCAG21/Understanding/animation-from-interactions.html
(Accessed: 18 September 2026).

All page copy, roast/origin details, pricing and team descriptions are
original content written for this project and are not drawn from an
external source.

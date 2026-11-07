# سُرعة — N1 Neon Arabesque mockup

Static, single-page marketing mockup built as a portfolio piece for the **Tenvora** design showcase.
Simulated domain: `suria.sa` — nothing here is a real product, real client, or real company.

## What the site is

A B2B payroll & payments landing page for small Saudi businesses. The page has one job: explain in three
steps how a salary transfer takes about three minutes (upload the payroll file → review and co-sign →
money reaches every local bank), and back it up with trust content — bank-grade security, dual approval,
immutable audit trail, a "what we never do" promise card, metrics, client voices, and an FAQ.

Copy is Modern Standard Arabic with a light Saudi business tone, written for a Riyadh persona.
There is no lorem ipsum, no external imagery, no backend, no admin route, no login.

## The design school — N1 Neon Arabesque

- Charcoal ground `#0B0E14`, neon cyan `#22D3EE`, gold `#F5C518`.
- Visual signature: Arabic kufic-style geometric line patterns (interlocking squares and orthogonal
  strokes) rendered as inline SVG `<pattern>` layers sitting behind the hero, steps, security, CTA and
  footer, faded with a mask and glowing subtly.
- Deep radial glows, thin 1px luminous rules between sections, generous negative space, a fine grain and
  vignette over the whole page.
- Type: `Reem Kufi` for display headings, `Tajawal` (400/500/700) for body.
- Arabic typographic rules applied: body line-height 1.82, headings 1.34–1.38, `letter-spacing: 0`
  globally (never kerned), base size never below 16px, Latin digits/labels isolated in LTR spans.

## Signature animation

A "money path": a kufic orthogonal SVG rail whose `stroke-dashoffset` is scrubbed by scroll
(GSAP ScrollTrigger), drawing itself right-to-left between the three step cards, with each node lighting
up as the line reaches it. The rail is fully drawn and all three nodes lit when GSAP is unavailable or
when the visitor asks for reduced motion, so the section never depends on JS to be readable.
On narrow screens the horizontal rail is replaced by a vertical CSS rail beside the stacked cards.

## Files

```
index.html          one page, dir="rtl" lang="ar"
assets/styles.css   hand-written CSS, logical properties only (no framework)
assets/app.js       nav, scroll rail, reveals, money path, counters, carousel, FAQ, form
```

## Scripts used

- Google Fonts: `Tajawal` + `Reem Kufi`
- GSAP 3.12.5 + ScrollTrigger (CDN, `defer`) — progressive enhancement only

## Interactions

- Sticky mirrored header, working hamburger below 900px (`aria-expanded`, Esc and outside click close it).
- Scroll progress hairline, active section link highlighting.
- Stats band counts up on scroll; reduced motion shows final values instantly.
- Testimonial carousel is static (no autoplay): buttons, dots, arrow keys (RTL-aware), Home/End.
- FAQ uses native `<details>/<summary>`; JS only closes siblings.
- One form: a work-email capture whose submit is intercepted and answered inline. No network request.
- Responsive at 380 / 768 / 1200; decorative overflow is clipped, no horizontal scrolling.

## Open locally

Double-click `index.html`, or serve the folder: `python -m http.server` then open the printed address.
No build step.

*من صناعة Tenvora*

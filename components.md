# Components — Live `/for-product/` Inventory

> **What this is:** a section-by-section teardown of the *current* live `revenuecat.com/for-product/` page (DOM-measured 2026-06-06), capturing the real component anatomy, copy, and specs. Companion to [`design.md`](design.md) (paste-ready tokens/recipes) and [`docs/08`](docs/08-brand-voice-and-visual-system.md) (rationale). **Use it two ways:** (1) as the baseline the new page replaces — note what to *keep* vs *cut*; (2) as the source of authentic component specs so the rebuild feels RC-ish.
>
> **Reminder (CLAUDE.md):** this is the *stale* page. The rebuild leads with jobs-to-be-done and the 3 wedges (velocity · completeness · forward-looking LTV) — do **not** clone this section order. Reuse the *visual grammar*, replace the *narrative*.

---

## A. Page skeleton (live section order, top → bottom)

| # | Section (live H1/H2) | Type | Keep / Cut / Rework for new page |
|---|---|---|---|
| 1 | **"You ship what matters, we handle monetization"** | Hero: headline + subhead + dual visual | **Rework** — keep the "you ship / we handle" relief framing; sharpen to velocity wedge ("ship monetization without shipping code") |
| 2 | For product teams (logo strip) | Trust row | **Rework** → real multi-logo band |
| 3 | Product teams that use RevenueCat | Testimonial (Mojo) | **Keep** — strong, named, quantified-ish |
| 4 | **A solid IAP foundation you can build on** | 7-item feature grid | **Cut to 3–4** — this is the feature-laundry-list the brief penalizes |
| 5 | Mojo's case study | Case study callout + "Read case study" | **Keep** — proof |
| 6 | **Explore the Dashboard** | 3-tab product tour (Charts / Customer mgmt / Customer Center) | **Rework** → tie to "source of truth / completeness" wedge |
| 7 | Proactively improve your product | Feature block | **Merge** into pillar narrative |
| 8 | **How it works** | 3-step (Configure → Connect SDK → Fetch/Subscribe/Unlock) | **De-emphasize** — this is dev-onboarding, not PM value; PMs don't write the SDK |
| 9 | **How teams use RevenueCat** | 5 role tiles (Marketing/Data/Product/Support/Engineering) | **Cut** — dilutes the PM focus the new page demands |
| 10 | **Ready to grow?** | Final CTA band | **Keep** — but rewrite to the eng-bottleneck payoff |
| — | Footer | 5-column mega-footer | **Keep** structure (simplify) |

**Critique takeaway:** the live page is *organized by feature/team*, not by PM jobs — and the 7-item "solid foundation" grid + 5-team grid are exactly the enumeration the brief warns against. The new page must synthesize these into 3–4 pillars.

---

## B. Measured component specs (real DOM values)

### Hero
- **H1:** Object Sans · 56px · weight **500** · letter-spacing **-2.24px** (-0.04em) · line-height 63px (1.125) · `#1F1F47`.
- **Subhead:** helveticaNeue · 20px · weight 300–400 · `#3D3D5C` · line-height 27.5px.
- **CTAs:** primary "Request a demo" (indigo pill) + secondary "Explore Product Demo" (borderless indigo text link).
- **Visual:** large product screenshot (~1033×841).
- → New build: swap copy to velocity wedge; keep the indigo-pill + text-link CTA pair (or upgrade secondary to bordered pill per `design.md` note).

### Section headings
- **H2 (display):** Object Sans · **40–56px** · weight **500** · tracking -0.04em · `#1F1F47`. *(Not 600 — RC headings are light.)*
- **H3 (feature title):** Object Sans · **24px** · weight **400** · tracking -0.96px (-0.04em) · line-height 33px.
- **H3 (team/role title):** Object Sans · 28px · weight 400.
- **Footer column headers:** Object Sans · 16px · weight 500.

### Body copy
- helveticaNeue (sub: Inter) · 16–20px · weight **300–400** · `#3D3D5C` · line-height ~1.4.

### Buttons / CTAs
| Variant | Live spec |
|---|---|
| **Primary** (Request a demo / Sign Up / Start for free) | indigo `#576DDB` bg · white text · **full pill** · padding `0 28–30px` (fixed height) · weight 500 · 15–16px |
| **Secondary** (Talk to sales / Get started / Explore Demo) | **borderless indigo text link** · padding 0 · weight 500 · radius 4px (none visible) |
| **Log In** | indigo text, weight 500 |

> The live secondary action is a text link, *not* a bordered pill. `design.md` deliberately upgrades it for the new page — that's a choice, not a measurement.

### Cards & elevation
- **Radii in play:** **4px** (dominant — 80×), **16px** (cards/icons), 32px, 64px, full-pill (buttons). **No 20px anywhere.**
- **Card shadow (measured):** `0 3px 16px rgba(73,46,107,0.14)` — a **purple-tinted** shadow, not neutral ink.
- **Elevated/float shadow:** `0 8px 48px rgba(0,0,0,0.15)`.
- Cards: white bg, hairline or borderless, generous padding (24px+).

### Color-as-accent — the real mechanism
- Solid brand colors are used sparingly: indigo for **every** CTA/link, coral for the wordmark + the occasional highlight, green for positive states.
- **Decorative pastel orbs:** large (~200px) circular blobs filled with the pastel tints — **coral `#F7D4D4`, indigo `#C1C9F6`, green `#C1F6E0`** — used as soft background decoration (full-pill radius). This is how RC gets color onto a white page without a wash. **`design.md` now carries these as `--rc-tint-*`.**

### Nav
- Sticky, white @ ~0.8 opacity + blur, hairline bottom border.
- Links: Why RevenueCat? · Solutions · Developers · Resources · Pricing (15px, weight 400, ink).
- Actions: **Log In** (indigo text) + **Sign Up** (indigo pill).
- Wordmark left.

### Testimonial (live, keep)
- Quote: *"We have gotten back so much time to focus on important features thanks to RevenueCat!"*
- Attribution: **Francescu Santoni, CTO at mojo.video** (80×80 avatar).
- → New build: `design.md`'s `.quote` recipe mirrors this; add a quantified outcome line.

### Footer
- 5 columns: Product · Solutions · Resources · Developers · Legal.
- Social: GitHub · X · Mastodon. © 2026 RevenueCat.

---

## C. Gaps between live page and `design.md` recipes

These `design.md` components are **synthesized** (good for the new page, but not lifted from *this* live page — flagged inline in `design.md`). Reviewing the **homepage** (`revenuecat.com/`, 2026-06-06) closes two of the three gaps — they're real RC patterns, just not on `/for-product/`:
- **Multi-logo trust band** — `/for-product/` shows a *single* customer (Mojo); the **homepage runs a repeating customer-logo carousel** (Notion, OpenAI, VSCO, Ladder, Runna…) that recurs ~3× down the page. ✅ Corroborated — use the band, optionally echo it near the final CTA.
- **Coral hero stat block** — `/for-product/` leads with a testimonial, no hero stat; the **homepage leads with a 3-up stat cluster** under the hero (~106k apps · 3B+ daily API requests · $14B+ revenue processed). ✅ Corroborated — prefer the *cluster* (3 numbers) over a lone stat.
- **Coin → dotted-line → hexagon signature diagram** — still synthesized; a RevenueCat *brand-wide* motif, not on either page as a literal component, but consistent with the homepage's preference for animated/SVG visuals over static screenshots.

Everything else in `design.md` (tokens, buttons, nav, two-up, tiles, testimonial, CTA band) is grounded in the measured `/for-product/` DOM above.

---

## E. Homepage cross-reference (`revenuecat.com/`, reviewed 2026-06-06)

The homepage is **not** the page we replace, but it shows RC at full brand strength and supplies patterns `/for-product/` lacks. Full principles are in [`design.md`](design.md) §5; the component-level deltas:

| Homepage component | What's distinct vs `/for-product/` | New-page use |
|---|---|---|
| **3-up stat cluster** (under hero) | `/for-product/` has no hero stat | hero → stat cluster → first pillar (`.stats`) |
| **Repeating logo carousel** | `/for-product/` shows one customer | trust band under hero, echo near final CTA |
| **Minimal case-study cards** | logo + **bold metric** + link; outcome over feature | proof beside each pillar (`.case`) |
| **Animated / SVG visuals** | `/for-product/` uses static screenshots | favor the coin→hexagon flow + light motion for pillar visuals |
| **Interleaved outcome threads** | homepage weaves use cases throughout, not feature-dump-then-testimonials | reinforces synthesize-don't-enumerate; keep proof adjacent to pillars |
| **Logo marquee + scroll fade-ins** | `/for-product/` is largely static | one ambient marquee + opacity reveals; see `design.md` §5 Motion |

### Homepage colors & motion (DOM-measured 2026-06-06 — corrects the first WebFetch read)

A `getComputedStyle` pass on `revenuecat.com/` (same method Track 8 used on `/for-product/`):

- **CTAs are indigo, not green.** Every button/link is indigo `#576DDB` (`rgb(87,108,219)`) — "Start for free", "Sign Up", "Talk to sales", "Read case study". The earlier WebFetch summary calling green a CTA color was **wrong**; discipline (indigo=CTA/link) holds on both pages.
- **Coral** = `#F2545B` text (19×) + a `#F25A5A` solid-block variant. **Pastel tints match our tokens exactly:** indigo `#C1C9F6`, coral `#F7D4D4`, green `#C1F6E0` (+ lighter green `#A6F2D2`). **Green is tint/positive-signal + gradient-endpoint only — never a CTA.**
- **Ink:** homepage uses a near-black **`#171A1C`** heavily for body/nav (≈92 nodes) alongside brand **`#1F1F47`** (≈65, headings), `#3D3D5C` muted (≈98), slate `#6C7693`. We keep `#1F1F47` as the single ink (logged, not adopting `#171A1C`).
- **Surfaces:** `#F9F9FB` dominant (45×), white, `#E3E6E8` hairline.
- **Gradients (new):** an **indigo→grey→green text-gradient** `linear-gradient(92deg, #5A73F2, #4D4D4D, #57DBA4)` — used **once** on the homepage, as `bg-clip:text` on the *secondary* headline **"Just one API"** (NOT the hero H1); a softer custom indigo/teal, not the exact brand colors. Plus a subtle card wash `linear-gradient(135deg, #EBEDF5, #FFFFFF)` and the logo-carousel **edge-fade mask** `linear-gradient(90deg, surface→transparent)`. → carried as `--rc-grad-text` / `--rc-grad-wash` in `design.md`.
- **Motion:** `@keyframes` present = **`logos`** (continuous marquee), `spin`, `contentShow`/`overlayShow` (Radix overlays). Transitions: hover `color/bg 0.3s cubic-bezier(.4,0,.2,1)`; **buttons faster `0.15s` via `filter` brightness** (not a color swap); scroll-reveal `opacity 0.5s/0.25s linear`; `transform 0.4s` lifts. → recipes in `design.md` §5 Motion.

---

## D. Build translation cheatsheet

| Live component | New-page role | Recipe in `design.md` |
|---|---|---|
| Hero headline+subhead+CTAs | Velocity-wedge hero | (write fresh; CTA pair recipe) |
| 7-item feature grid | → 3–4 pillar two-ups | `.two-up` (alternating) |
| Dashboard 3-tab tour | Completeness/source-of-truth pillar | `.two-up` + `.tile` |
| How-it-works 3-step | De-emphasized / footnote | `.tile` row |
| Mojo testimonial | Proof beside relevant pillar | `.quote` |
| Final CTA band | Closing eng-bottleneck payoff | `.cta-band` (optional dark) |
| Pastel orbs | Background accent on white | `--rc-tint-*` circles |

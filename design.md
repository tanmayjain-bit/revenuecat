# Design — Build Handbook

> **Source of truth:** [`docs/08-brand-voice-and-visual-system.md`](docs/08-brand-voice-and-visual-system.md) — the full rationale, measured-from-live tokens, voice do/don't, and licensing notes live there. **This file is the build-facing quick-reference**: paste-ready tokens + component recipes for when we build the landing page (Track 9). If the two ever disagree, `docs/08` wins.

Most values below were **measured from the live `revenuecat.com/for-product/` DOM** (2026-06-06) and re-verified against the computed DOM. A few items are **synthesized for the new page** (built on RC's brand language but not lifted from the `/for-product/` page) and are flagged inline as *(synthesized)* — the coin→hexagon signature diagram (a brand-wide RC motif). Two formerly-synthesized items — the **multi-logo trust band** and the **hero stat block** — are now **corroborated by the homepage** (`revenuecat.com/`, reviewed 2026-06-06): the homepage leads with a 3-up stat cluster under the hero and a repeating customer-logo carousel, so these are RC patterns, just not ones the `/for-product/` page happens to use. See §5 for the homepage-derived principles. Stack assumption: a static/React page with Tailwind or plain CSS; recipes are framework-light so they port either way.

---

## 1. Tokens (paste into `:root` / Tailwind theme)

```css
:root {
  /* Brand */
  --rc-coral:      #F2545B;  /* logo + sparing accent + key stat numbers */
  --rc-coral-ink:  #D63B43;  /* coral text-on-light / hover */
  --rc-indigo:     #576DDB;  /* PRIMARY CTA + links */
  --rc-indigo-700: #3F53C0;  /* CTA hover/active */
  --rc-green:      #11D483;  /* success / positive only — never a CTA */

  /* Ink & text */
  --rc-ink:        #1F1F47;  /* headings AND body */
  --rc-ink-70:     #3D3D5C;  /* muted body / captions (live-DOM dominant muted ink) */
  --rc-ink-45:     #8A8AA3;  /* labels, eyebrows, disabled */

  /* Surfaces (hexes corrected to exact live-DOM values 2026-06-06) */
  --rc-bg:         #FFFFFF;
  --rc-surface:    #F9F9FB;  /* card / section tint */
  --rc-surface-2:  #EEEFF6;  /* nested card / input fill */
  --rc-border:     #EAEDF6;  /* hairlines */
  --rc-ink-surface:#16162E;  /* optional dark band */

  /* Pastel accent tints — the live page's real "color as accent" mechanism.
     Use as full-block / chip fills behind a feature, NOT as text color. */
  --rc-tint-coral:  #F7D4D4;
  --rc-tint-indigo: #C1C9F6;
  --rc-tint-green:  #C1F6E0;

  /* Type */
  --rc-font-head: "Hanken Grotesk", "Manrope", ui-sans-serif, system-ui, sans-serif;
  --rc-font-body: "Inter", "Helvetica Neue", Helvetica, Arial, ui-sans-serif, system-ui, sans-serif;

  /* Shape (corrected to live DOM: dominant radii are 4px + 16px; NO 20px exists on live) */
  --rc-radius-pill: 999px;   /* buttons + chips are FULL pills (a core RC tell) */
  --rc-radius-card: 16px;    /* cards — RC corners are crisper than they look */
  --rc-radius-icon: 16px;
  --rc-radius-sm:   4px;     /* the most-used radius on live: inputs, tags, small UI */

  /* Elevation (live DOM uses a PURPLE-tinted shadow, not neutral ink) */
  --rc-shadow-card:  0 3px 16px rgba(73,46,107,0.14);   /* measured live card shadow */
  --rc-shadow-float: 0 8px 48px rgba(0,0,0,0.15);       /* measured live elevated shadow */

  /* Rhythm (8pt base) */
  --rc-section-y: clamp(72px, 9vw, 128px);
  --rc-gutter:    clamp(20px, 4vw, 80px);
  --rc-maxw:      1200px;

  /* Gradients (measured from homepage DOM 2026-06-06) */
  --rc-grad-text: linear-gradient(92deg, #5A73F2 -14%, #4D4D4D 56%, #57DBA4 105%); /* indigo→grey→green text-gradient. RC uses it via bg-clip:text on ONE *secondary* headline ("Just one API") — NOT the hero H1. Optional single accent; off-brand if overused (its endpoints aren't the exact brand indigo/green). */
  --rc-grad-wash:      linear-gradient(135deg, #EBEDF5, #FFFFFF);  /* subtle card / section wash */

  /* Motion (measured easing + durations from homepage) */
  --rc-ease:        cubic-bezier(0.4, 0, 0.2, 1); /* standard easing — used site-wide */
  --rc-dur-hover:   0.3s;   /* link / text color hover */
  --rc-dur-btn:     0.15s;  /* button hover (bg + filter brightness) */
  --rc-dur-reveal:  0.5s;   /* scroll fade-in */
  --rc-dur-lift:    0.4s;   /* card / element transform */
}
```

**Fonts (deployable subs — RC's Object Sans is paid, don't ship it):**

```html
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Hanken+Grotesk:wght@400;500;600;700&family=Inter:wght@400;500;600&display=swap" rel="stylesheet">
```

**Palette discipline:** white + ink base. Color is accent, not wash → **indigo** = every CTA/link, **coral** = one highlight + key numbers, **green** = positive signals only. Optional single dark-ink band. The one sanctioned exception to "ink + accents only": the three **pastel tints** above, used as soft *full-block or chip fills* behind a feature (this is exactly how the live page applies color at scale) — never as text. Keep solid brand colors for text/CTAs; reserve tints for backgrounds.

**Type scale (corrected to live DOM — RC headings run LIGHT, ~500/400, never 600/700, with tight `-0.04em` tracking):** H1 `clamp(40px,6vw,72px)`/**500**/`-0.04em`/1.125 (live = 56px/500/-2.24px/63px) · H2 `clamp(40px,5vw,56px)`/**500**/`-0.04em`/1.12 (live = 40–56px/500) · H3 `24px`/**400**/`-0.04em`/1.38 (live feature titles; team titles 28px/400) · body `20px`/**300–400**/1.4/`--rc-ink-70` · caption 13–14px/500/`--rc-ink-45`. *Resist the urge to bold headings — RC's restraint is the weight-500 display + weight-400 sub-heads.*

---

## 2. Component library (meaningful components)

Class names are illustrative; map to Tailwind utilities or your CSS. Each maps 1:1 to the component table in `docs/08`.

### Buttons — full pill, weight 500

```html
<a class="btn btn--primary" href="/signup">Start for free</a>
<a class="btn btn--secondary" href="/demo">Talk to sales</a>
```
```css
.btn { display:inline-flex; align-items:center; gap:8px; font-family:var(--rc-font-head);
       font-weight:500; font-size:16px; padding:14px 30px; border-radius:var(--rc-radius-pill);
       transition:.15s ease; cursor:pointer; }
.btn--primary   { background:var(--rc-indigo); color:#fff; border:1px solid transparent; }
.btn--primary:hover   { background:var(--rc-indigo-700); }
.btn--secondary { background:transparent; color:var(--rc-ink); border:1px solid var(--rc-border); }
.btn--secondary:hover { background:var(--rc-surface); }
```
> **Dual-CTA pair** (primary self-serve + secondary sales) is the recurring CTA — serves SMB + enterprise on one page. Repeat it at hero, mid-page, and final CTA.
> **Note on the live pattern:** on `/for-product/` the secondary action is usually a *borderless indigo text link* ("Talk to sales", "Explore Product Demo"), not a bordered pill. The bordered `.btn--secondary` above is a deliberate upgrade for the new page (gives enterprise a clearer second button). If you want to match live exactly, drop the border + background and render it as a plain indigo link (weight 500).

### Eyebrow chip — pill label above a headline

```html
<span class="eyebrow">For product managers</span>
```
```css
.eyebrow { display:inline-block; font-family:var(--rc-font-head); font-weight:500; font-size:13px;
           letter-spacing:.02em; color:var(--rc-ink-70); background:var(--rc-surface);
           padding:6px 14px; border-radius:var(--rc-radius-pill); }
```

### Nav — sticky, wordmark left, indigo pill right

```html
<header class="nav">
  <a class="nav__logo" href="/">RevenueCat</a>
  <nav class="nav__links">
    <a href="#pillars">Why RevenueCat</a><a href="#proof">Customers</a><a href="#pricing">Pricing</a>
  </nav>
  <div class="nav__actions">
    <a href="/login">Log In</a>
    <a class="btn btn--primary" href="/signup">Sign Up</a>
  </div>
</header>
```
```css
.nav { position:sticky; top:0; z-index:50; display:flex; align-items:center; justify-content:space-between;
       padding:16px var(--rc-gutter); background:rgba(255,255,255,.85); backdrop-filter:blur(8px);
       border-bottom:1px solid var(--rc-border); }
.nav__logo { font-family:var(--rc-font-head); font-weight:700; color:var(--rc-coral); font-size:22px; }
```

### Two-up section — copy + visual, alternate L/R down the page

```html
<section class="section">
  <div class="section__inner two-up">
    <div class="two-up__copy">
      <span class="eyebrow">Paywalls</span>
      <h2>Change your paywall without shipping an app update.</h2>
      <p>Edit pricing, layout, and offers remotely — and ship on your own cadence, no eng sprint required.</p>
      <a class="btn btn--primary" href="/signup">Start for free</a>
    </div>
    <div class="two-up__visual"><!-- product UI shot / diagram --></div>
  </div>
</section>
```
```css
.section { padding-block:var(--rc-section-y); }
.section__inner { max-width:var(--rc-maxw); margin-inline:auto; padding-inline:var(--rc-gutter); }
.two-up { display:grid; grid-template-columns:1fr 1fr; gap:clamp(32px,5vw,80px); align-items:center; }
.two-up--reverse .two-up__copy { order:2; }     /* alternate direction */
@media (max-width:768px){ .two-up{ grid-template-columns:1fr; } }
```

### Feature tile — icon coin + title + one-line benefit

```html
<article class="tile">
  <div class="tile__icon"><!-- line/duotone icon --></div>
  <h3>Predicted LTV</h3>
  <p>See the 12-month winner before the experiment finishes.</p>
</article>
```
```css
.tile { background:var(--rc-bg); border:1px solid var(--rc-border); border-radius:var(--rc-radius-card);
        padding:28px; box-shadow:var(--rc-shadow-card); }
.tile__icon { width:48px; height:48px; display:grid; place-items:center; border-radius:var(--rc-radius-icon);
              background:var(--rc-surface); box-shadow:var(--rc-shadow-card); margin-bottom:16px; }
.tile h3 { font-family:var(--rc-font-head); font-weight:400; font-size:20px; margin:0 0 6px; }  /* RC feature titles run LIGHT (measured 400) — never 600 */
.tile p  { color:var(--rc-ink-70); margin:0; }
```

### Stat block / cluster — quantified proof *(corroborated by homepage — `/for-product/` leads with a testimonial, but `revenuecat.com/` leads with a 3-up stat cluster under the hero)*

The homepage anchors credibility with a **3-up stat cluster** directly under the hero (live: ~106k apps · 3B+ daily API requests · $14B+ revenue processed). Prefer this cluster form over a lone stat — three numbers read as scale, one reads as a brag. Use coral only on the *number*, ink-45 on the caption.

```html
<div class="stats">
  <div class="stat"><span class="stat__num">~1/3</span><span class="stat__cap">of new subscription apps run on RevenueCat<sup>*</sup></span></div>
  <div class="stat"><span class="stat__num">$X B+</span><span class="stat__cap">revenue processed</span></div>
  <div class="stat"><span class="stat__num">XB+</span><span class="stat__cap">API requests / day</span></div>
</div>
```
```css
.stats { display:flex; flex-wrap:wrap; gap:clamp(32px,5vw,72px); justify-content:center; }
.stat__num { display:block; font-family:var(--rc-font-head); font-weight:700; font-size:clamp(40px,5vw,64px);
             color:var(--rc-coral); letter-spacing:-.03em; }
.stat__cap { color:var(--rc-ink-45); font-size:14px; }
```
> Attribute vendor-reported numbers (e.g. "per Bain Capital Ventures"). Don't inflate — this audience distrusts unmeasurable claims. Verify any number against the fact-sheet / brief before it ships; the live homepage figures above are the *pattern*, not pre-approved copy.

### Case-study card — minimal: logo + bold metric + link *(homepage pattern)*

The homepage's case-study cards are deliberately spare: a customer logo, **one bold outcome metric**, and a "Read case study" link — outcome over feature list. Use as a row of 2–3 beside or after a pillar.

```html
<a class="case" href="#">
  <img class="case__logo" src="" alt="">
  <span class="case__metric">−40% billing maintenance time</span>
  <span class="case__link">Read case study →</span>
</a>
```
```css
.case { display:flex; flex-direction:column; gap:12px; background:var(--rc-surface); border-radius:var(--rc-radius-card);
        padding:28px; text-decoration:none; }
.case__metric { font-family:var(--rc-font-head); font-weight:600; font-size:24px; color:var(--rc-ink); letter-spacing:-.03em; }
.case__link   { color:var(--rc-indigo); font-weight:500; font-size:14px; }
```

### Logo band — social proof under the hero *(corroborated by homepage — it runs a repeating customer-logo carousel; `/for-product/` shows a single customer)*

```html
<section class="logos">
  <p class="logos__label">Trusted by the teams behind</p>
  <div class="logos__row"><!-- mono/greyscale customer logos --></div>
</section>
```
```css
.logos { padding-block:48px; text-align:center; }
.logos__label { color:var(--rc-ink-45); font-size:14px; margin-bottom:20px; }
.logos__row { display:flex; flex-wrap:wrap; gap:40px; justify-content:center; align-items:center;
              filter:grayscale(1); opacity:.7; }
```

### Testimonial card — quote + attribution + outcome

```html
<figure class="quote">
  <blockquote>"We got back so much time to focus on the features that matter."</blockquote>
  <figcaption><img src="" alt=""><span><strong>Name</strong>, Role · Company</span></figcaption>
  <p class="quote__metric">−40% time spent on billing maintenance</p>
</figure>
```
```css
.quote { background:var(--rc-surface); border-radius:var(--rc-radius-card); padding:32px; }
.quote blockquote { font-family:var(--rc-font-head); font-size:22px; line-height:1.4; margin:0 0 20px; }
.quote__metric { color:var(--rc-coral-ink); font-weight:600; margin-top:16px; }
```

### Signature diagram — icon coins → dotted lines → RC hexagon *(synthesized — brand-wide RC motif, not on `/for-product/`)*

The most on-brand custom visual: rounded-square "coins" (Apple / Android / Web) connected by **dotted lines** into a central hexagon **RC** mark, fanning out to customer states (✓ active, ↻ renewed, ✕ churned). For the new page, build it as the **ad → funnel → checkout → redemption** flow. Coins use `--rc-radius-icon` + `--rc-shadow-card`; dotted connectors in `--rc-border`; success badges in `--rc-green`. SVG or absolutely-positioned divs both fine.

### CTA band — repeated conversion beat

```html
<section class="cta-band">
  <h2>Ready to ship monetization without the eng bottleneck?</h2>
  <div class="cta-band__actions">
    <a class="btn btn--primary" href="/signup">Start for free</a>
    <a class="btn btn--secondary" href="/demo">Talk to sales</a>
  </div>
</section>
```
> Optionally render this (and the footer) on `--rc-ink-surface` (`#16162E`) for one dramatic dark band; flip text to white and keep the indigo primary button.

---

## 3. Voice cheat-sheet (full version in `docs/08` §Voice & tone)

- **Construction:** verb-first / "you"-led → concrete capability → quantified payoff. "Stop wasting time on X — do Y instead."
- **Do:** conversion, LTV, retention, ARR, churn · "without an app update" · "no engineering required" · "on your own cadence" · named proof + real numbers.
- **Don't:** "growth/synergy/revolutionary/seamless/unlock/supercharge," unquantified AI hype, a feature named without its benefit, anything unmeasurable.
- **Register:** lead emotional (relief / get-your-time-back), close logical (the number). Build-vs-buy: respectful, then defeat it with real cost/maintenance reality.

---

## 4. Build checklist (Track 9)

- [ ] Tokens in `:root`; Hanken Grotesk + Inter loaded.
- [ ] White/ink base; indigo CTAs, coral accents, green positives only.
- [ ] Pill buttons + chips; 16px soft cards (purple-tinted shadow); LIGHT headings (500/400, never 600+); two-up alternating sections; big vertical rhythm.
- [ ] Homepage patterns: 3-up stat cluster under hero; repeating logo marquee (edge-fade mask, echoed near close); minimal case cards; scroll-reveal + brightness-hover motion (all degrade gracefully).
- [ ] Dual-CTA at hero / mid-page / final.
- [ ] Signature coin→hexagon diagram built as the funnel flow.
- [ ] Every headline & CTA passes the voice do/don't.
- [ ] Responsive: two-up collapses to single column ≤768px; tap targets ≥44px.
- [ ] Deployable (Vercel/Netlify) — no licensed fonts shipped.
```

---

## 5. Homepage-derived principles (`revenuecat.com/`, reviewed 2026-06-06)

The `/for-product/` page is our baseline, but the **homepage** carries a few brand-level patterns that page doesn't — worth borrowing because they're how RC presents itself at full strength. None of these override the palette/voice discipline above; they're structural.

- **Lead with scale, then story.** The homepage anchors a **3-up stat cluster** under the hero *before* any feature copy (apps · API requests/day · revenue processed). Mirror this: hero → stat cluster → first pillar. Numbers buy permission to make claims. (Recipe: `.stats` in §2.)
- **Repeating logo carousel, not a one-time wall.** Recognizable customer logos (Notion, OpenAI, VSCO, Ladder, Runna…) **cycle and recur 3× down the page**, creating rhythm without a static logo graveyard. For our single page, place the trust band under the hero and optionally echo a slimmer logo row near the final CTA.
- **Outcomes over features, interleaved.** The homepage threads use-case/outcome narratives *throughout* (engineering · marketing · product · data) rather than a feature-dump-then-testimonials structure. Case-study cards lead with a **bold business metric** (churn ↓, eng hours saved), not a feature name. This reinforces our synthesize-don't-enumerate rule — keep proof adjacent to each pillar. (Recipe: `.case` in §2.)
- **Motion / live visuals over static screenshots.** The homepage uses animated/SVG graphic areas rather than flat product screenshots, reading as "dynamic, not legacy." Favor the signature coin→hexagon flow diagram and lightweight animated/SVG visuals for our pillar visuals where feasible; static shots are the fallback, not the goal.
- **Indigo is the CTA color here too — discipline confirmed (DOM-measured 2026-06-06).** Contrary to the first WebFetch summary, the homepage's CTAs/links are **indigo `#576DDB`** (every "Start for free"/"Sign Up"/"Talk to sales"/"Read case study"), exactly like `/for-product/`. Coral is `#F2545B` (with a `#F25A5A` solid-block variant); the three pastel tints match our tokens exactly. **Green is NOT a CTA** — it appears only as (a) a pastel tint background (`#C1F6E0`, lighter `#A6F2D2`) and (b) the green endpoint of the signature gradient. Our discipline holds verbatim: **indigo = CTAs/links, coral = highlight + key numbers, green = positive-signal/tint only.**
- **Two ink neutrals coexist.** The homepage leans on a near-black **`#171A1C`** for a large share of body/nav text (≈92 nodes), alongside our brand ink-navy **`#1F1F47`** (≈65, mostly headings) and `#3D3D5C` muted body (≈98) + a slate `#6C7693`. We **keep `#1F1F47` as the single ink** for brand cohesion (it's what `/for-product/` uses); `#171A1C` is logged as the homepage's choice, not adopted — flag it only if a future review wants higher body contrast.
- **One text-gradient exists — and RC uses it sparingly.** `--rc-grad-text` (indigo→grey→green, `92deg`) appears **exactly once** on the homepage: as `background-clip:text` on a *secondary* feature headline, **"Just one API"** — **not** on the hero H1. So it's a small, single-use accent, not a "signature sweep," and its endpoints (`#5A73F2`/`#57DBA4`) are a softer custom indigo/teal, not the exact brand `#576DDB`/`#11D483`. If used at all, put it on one lower-stakes headline, never the primary H1, never a section wash. The subtle `--rc-grad-wash` (`135deg #EBEDF5→#FFFFFF`) is the safe, frequent one for cards/section tints.

### Motion (measured from homepage DOM — durations/easing are real, not invented)

RC's motion is **restrained and functional** — no decorative bounce. Four patterns, all on the standard easing `--rc-ease` `cubic-bezier(.4,0,.2,1)`:

1. **Logo marquee** (`@keyframes logos`) — the customer-logo carousel scrolls continuously, horizontally, with a **fade mask at both edges** (`linear-gradient(90deg, surface→transparent)`), so logos dissolve rather than clip. This is the page's one piece of ambient motion.
2. **Scroll-reveal fade-in** — content fades in on scroll via `opacity` transitions (`--rc-dur-reveal` 0.5s, some 0.25s, `linear`). Subtle opacity-only (optionally a small `translateY`), not a slide-and-bounce. Gate behind `prefers-reduced-motion`.
3. **Hover** — links/text transition `color` over `--rc-dur-hover` (0.3s); **buttons** are faster (`--rc-dur-btn` 0.15s) and shift via **`filter` brightness** + background, not a hard color swap → a softer "press." Add a small `transform` lift (`--rc-dur-lift` 0.4s) on cards.
4. **Overlays** (`contentShow`/`overlayShow`, Radix-style) — nav dropdowns/dialogs fade+scale in. Only relevant if we ship a dropdown nav (we likely won't on a single page).

```css
/* Scroll-reveal — respect reduced motion */
.reveal { opacity:0; transform:translateY(12px); transition:opacity var(--rc-dur-reveal) linear, transform var(--rc-dur-reveal) var(--rc-ease); }
.reveal.is-in { opacity:1; transform:none; }
@media (prefers-reduced-motion: reduce){ .reveal{ opacity:1; transform:none; transition:none; } }

/* Logo marquee */
@keyframes rc-marquee { from{ transform:translateX(0);} to{ transform:translateX(-50%);} }
.logos__row--marquee { animation:rc-marquee 30s linear infinite; }
.logos--mask { -webkit-mask-image:linear-gradient(90deg,transparent,#000 8%,#000 92%,transparent); mask-image:linear-gradient(90deg,transparent,#000 8%,#000 92%,transparent); }

/* Button hover — brightness filter, not a color swap */
.btn--primary{ transition:background-color var(--rc-dur-btn) var(--rc-ease), filter var(--rc-dur-btn) var(--rc-ease); }
.btn--primary:hover{ filter:brightness(1.06); }
```
> **Keep motion cheap and optional.** Marquee + fade-in are the only two worth building; both must degrade gracefully (no JS → logos static; reduced-motion → no fade). Don't add parallax, scroll-jacking, or autoplay video — off-brand and a perf/CWV risk on a single static page.

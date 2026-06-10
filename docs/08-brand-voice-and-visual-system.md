# Track 8 — Brand, Voice & Visual System

**Job:** Capture how RevenueCat looks and sounds so the refreshed page reads as **"RevenueCat-ish"** — brand-aware, not pixel-perfect. Two halves: a **visual system** (design tokens the build reuses) and a **copy voice** (do/don't the writing follows).

**Reference (captured live 2026-06-06):** https://www.revenuecat.com and https://www.revenuecat.com/for-product/ — homepage WebFetch + a Chrome DevTools screenshot and `getComputedStyle` pass on `/for-product/` for exact tokens. Values below are **measured from the live DOM**, not guessed.

> **Guardrail (from the brief):** exact alignment isn't required and you're not expected to be a designer. Aim for *palatable + coherent + recognizably RevenueCat*. Where a brand asset is licensed (the Object Sans headline face), this doc specifies a free, near-identical substitute so the build stays legal and deployable.

---

## Visual system

### Design tokens (measured from the live site)

These are written as CSS custom properties so Track 9 can paste them into a `:root` / Tailwind theme directly.

```css
:root {
  /* ---- Brand ---- */
  --rc-coral:        #F2545B;  /* logo wordmark + the signature accent. Use SPARINGLY: logo, one
                                  highlight per section, key stat numbers. This is the "RevenueCat red." */
  --rc-coral-ink:    #D63B43;  /* darker coral for text-on-light / hover on coral */
  --rc-indigo:       #576DDB;  /* PRIMARY CTA color (measured rgb(87,109,219)). Buttons, links. */
  --rc-indigo-700:   #3F53C0;  /* indigo hover/active */
  --rc-green:        #11D483;  /* success / "it works" accent — checkmarks, positive deltas, the
                                  green sync badge in the hero diagram. Secondary, never a CTA. */

  /* ---- Ink & text (measured rgb(31,31,71)) ---- */
  --rc-ink:          #1F1F47;  /* headings AND body copy — RC uses one deep navy-ink for both */
  --rc-ink-70:       #4B4B6B;  /* muted body / captions */
  --rc-ink-45:       #8A8AA3;  /* labels, eyebrows, disabled */

  /* ---- Surfaces ---- */
  --rc-bg:           #FFFFFF;  /* page background — bright, airy, lots of whitespace */
  --rc-surface:      #F7F7FA;  /* card / section-tint / soft panel (cool near-white) */
  --rc-surface-2:    #EEEFF6;  /* nested card, input fill, hairline fills */
  --rc-border:       #E4E5EE;  /* hairline borders on cards/dividers */
  --rc-ink-surface:  #16162E;  /* OPTIONAL dark band (footer / one dramatic section) */

  /* ---- Type ---- */
  --rc-font-head: "Object Sans", "Hanken Grotesk", "Manrope", ui-sans-serif, system-ui, sans-serif;
  --rc-font-body: "Inter", "Helvetica Neue", Helvetica, Arial, ui-sans-serif, system-ui, sans-serif;

  /* ---- Radius & shape ---- */
  --rc-radius-pill:  999px;    /* buttons + eyebrow chips are FULLY rounded pills — a core RC tell */
  --rc-radius-card:  20px;     /* cards / feature tiles: large, soft corners */
  --rc-radius-icon:  16px;     /* the rounded-square icon "coins" in the hero diagram */

  /* ---- Elevation ---- */
  --rc-shadow-card:  0 8px 30px rgba(31,31,71,0.06);
  --rc-shadow-float: 0 12px 40px rgba(31,31,71,0.10);

  /* ---- Spacing rhythm (8pt base) ---- */
  --rc-section-y:    clamp(72px, 9vw, 128px);  /* vertical breathing room between sections */
  --rc-gutter:       clamp(20px, 4vw, 80px);   /* page side padding */
  --rc-maxw:        1200px;                     /* content max-width */
}
```

**Palette intent:** the page is **white and airy** with **ink-navy** type. Color is an *accent*, not a wash — **coral** for one highlight per section + key numbers, **indigo** for every CTA/link, **green** only for "this works / positive" signals. Optionally one **dark ink band** (footer or a single dramatic build-vs-buy / proof section) for contrast. Don't introduce colors outside this set.

### Type

| Role | Font | Weight | Size (desktop) | Tracking / leading | Notes |
|---|---|---|---|---|---|
| H1 / hero | Object Sans (sub: Hanken Grotesk) | 500 | 56–72px, `clamp(40px,6vw,72px)` | `-0.04em`, line-height ~1.05 | **Measured:** 56px/500/`-2.24px`. Geometric, *medium* not black — confident, not shouty. |
| H2 / section | Object Sans | 500–600 | 32–44px | `-0.03em`, ~1.1 | One idea per section headline. |
| H3 / card title | Object Sans | 600 | 20–22px | `-0.01em` | Feature/pillar tile titles. |
| Eyebrow / chip | Object Sans | 500 | 13–14px | `+0.02em`, UPPERCASE optional | Lives in a pill chip (see hero "For product teams"). |
| Body | Inter (sub: Helvetica Neue) | 400 | 17–18px | ~1.55 | RC body is plain Helvetica Neue; Inter is the deployable match. |
| Caption / label | Inter | 500 | 13–14px | ~1.4, `--rc-ink-45` | Stat captions, footnotes. |

> **Licensing note:** **Object Sans** is a paid Pangram Pangram face — do **not** ship it. Use **Hanken Grotesk** or **Manrope** (Google Fonts, free) for headings; both are geometric grotesques that read near-identically at display sizes. Body **Helvetica Neue** → **Inter** (free, ubiquitous). This keeps the build deployable and "RevenueCat-ish" without lifting a licensed asset.

### Layout language

- **Grid:** centered `max-width: 1200px`, generous side gutters, 12-col mental model. Most sections are **two-up**: copy on one side, a product shot / diagram on the other, alternating L/R down the page.
- **Section rhythm:** big vertical padding (`--rc-section-y`), one H2 + short subhead + supporting visual + (often) a CTA per section. The live page's reusable beat is **H2 → short body → small feature row → CTA** — Track 4 flagged this rhythm as a *keep*. Reuse it, but fill it with story-led (pillar) content, not a feature grid.
- **Cards/tiles:** white or `--rc-surface` fill, `--rc-radius-card` (20px), hairline `--rc-border` or soft `--rc-shadow-card`, roomy internal padding (24–32px). Feature tiles lead with a **rounded-square icon coin** (`--rc-radius-icon`, soft shadow) then title + one-line benefit.
- **Whitespace is the brand.** When unsure, add space. Don't crowd; don't fill every column.

### Imagery & motion

- **Product UI shots** are the hero asset — show the real dashboard (Charts, Paywall builder, Experiments) the way the live "Explore the Dashboard" block does. Track 4: expand product-show to Paywalls/Experiments UI.
- **Diagrams** in the house style = **rounded-square icon "coins" connected by dotted lines** into a central hexagon "RC" mark (see the hero: Apple / Android / Web → RC → customer states). This **ad → funnel → checkout → redemption** flow diagram is the single most on-brand custom visual to build for the new page.
- **Iconography:** simple line/duotone icons inside the rounded-square coins; platform glyphs (Apple, Android, Web) in their familiar colors; green check / red x state badges.
- **Motion:** restrained — subtle fade/translate-up on scroll, a number count-up on key stats, light hover lift on cards. Nothing flashy; the audience distrusts spectacle (Track 1).

### Components (the recurring patterns the page reuses)

| Component | Spec |
|---|---|
| **Primary button** | `--rc-indigo` fill, white text, **full pill** (`--rc-radius-pill`), weight 500, padding ~`14px 30px`, hover → `--rc-indigo-700`. (Measured from the live "Sign Up".) |
| **Secondary button** | Ghost/outline: `--rc-border` 1px, `--rc-ink` text, pill, transparent → `--rc-surface` on hover. The **dual-CTA pair** (primary "Start for free" + secondary "Talk to sales") is a Track-4 *keep* — serves SMB + enterprise. |
| **Eyebrow chip** | Pill, `--rc-surface` fill, small Object-Sans label (e.g. "For product managers"). Sits above H1/H2. |
| **Feature tile** | Card + icon coin + H3 + one-line benefit (+ optional link). Used in pillar evidence rows. |
| **Stat block** | Big coral/ink number (Object Sans) + small `--rc-ink-45` caption. For quantified proof (Track 7). |
| **Logo band** | Greyscale/mono customer logos on `--rc-bg` or `--rc-surface`, label above ("Trusted by the teams behind…"). Track 4: keep placement, upgrade to marquee logos. |
| **Testimonial card** | Quote + avatar + name/role/company + (ideally) a quantified outcome. |
| **Nav** | Sticky, white, wordmark left, center links, right = "Log In" (text) + "Sign Up" (indigo pill). |
| **Section divider** | Whitespace or hairline `--rc-border`; optional `--rc-surface` tint to separate beats. |

---

## Voice & tone

### How RevenueCat talks

Clear, **technical-but-accessible**, confident, results-oriented, **not buzzword-y**. Short declarative sentences. Leads with the job/outcome, names the mechanism plainly, backs it with a number. Speaks *to* a competent operator — never hypes, never condescends.

**Live homepage samples (verbatim — match this register):**
- "You ship what matters, we handle monetization"
- "Cross-platform purchases built better and faster"
- "Stop spending time on platform updates and edge cases — build great features instead."
- "Your subscription backend-in-a-box"
- "Build, target & test paywalls that convert"
- "Understand what drives growth & do more of it"

**Pattern to notice:** *imperative or "you"-led* → *concrete capability* → *implied payoff*. "Stop wasting time on X, do Y instead" is a recurring construction (the hero literally uses it). Headlines are **medium-weight, plain-language, verb-first** — never adjective soup.

### Vocabulary — do / don't (cross-ref Track 1)

**Do** — the language PMs trust:
- Concrete outcomes: **conversion, LTV, retention, ARR, ARPU, churn**.
- **Quantified** claims and **time saved** ("ship a paywall change in minutes," "without an app release").
- Velocity/ownership: **"no engineering required," "without an app update," "on your own cadence," "source of truth."**
- **Named, specific** proof (real brands, real numbers).
- Plain mechanism words: **paywall, experiment, predicted LTV, web checkout, targeting rule**.

**Don't** — language this audience distrusts:
- Vague **"growth," "synergy," "revolutionary," "seamless," "unlock," "supercharge."**
- **Unquantified AI hype** ("AI-powered" with no payoff). If AI appears, it must do a measurable job.
- **Feature jargon without a benefit** — never name a feature without the job it gets done.
- Anything **unmeasurable** — claims the reader can't verify read as marketing noise to a PM.

### Tone by section (calibration)

- **Hero / pillars:** confident + benefit-led. Lead with the JTBD, one tight sentence.
- **Proof / stats:** factual, quiet, let the numbers carry it (Track 1 distrusts overclaiming; Track 7 / fact-sheet note RC scale numbers are vendor-reported — attribute, don't inflate).
- **Build-vs-buy:** respectful and direct — acknowledge "you could build this" before defeating it. No fear-mongering; use the real cost/maintenance reality.
- **Emotional register (from fact-sheet G-VoC):** you may *open* on **relief** ("get your time back," stop hand-rolling StoreKit) and **frustration** (billing is undifferentiated grunt work) — then immediately ground it in a logical, quantified payoff. Lead emotional, close logical.

### Micro do/don't (for copy QA)

| ✅ Do write | ❌ Don't write |
|---|---|
| "Change your paywall without shipping an app update." | "Unlock seamless monetization growth." |
| "Predicted 12-month LTV picks the winning price." | "AI-powered revenue optimization." |
| "Powers ~1/3 of new subscription apps (per Bain Capital Ventures)." | "The world's #1 revolutionary platform." |
| "Ship pricing experiments on your own cadence." | "Supercharge your synergy." |

---

## Output — quick-reference for the build (Track 9)

1. Paste the `:root` token block into the stylesheet / Tailwind theme.
2. Headings **Hanken Grotesk** (or Manrope), body **Inter** — both Google Fonts, deployable; they substitute the licensed Object Sans / Helvetica Neue.
3. **White + ink-navy** base; **indigo** = every CTA/link, **coral** = one accent + key numbers, **green** = positive signals only; optional one dark ink band.
4. **Pill** buttons + chips, **20px** cards with soft shadow, **two-up alternating** sections, big vertical rhythm, the **icon-coin → dotted-line → RC hexagon** diagram as the signature visual.
5. Voice: verb-first, "you"-led, quantified; obey the do/don't lists above in every headline and CTA.

*This is a lightweight style reference, not a full design system — consistent with the brief's "brand-aware, not pixel-perfect" guardrail.*

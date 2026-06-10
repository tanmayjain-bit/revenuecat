# Track 4 — Current-Page Teardown (Baseline)

**Focus (live-page audit only):** the brief says `/for-product/` is "stale" — audit it so the refresh is a deliberate before→after. Audience → [01](01-audience-research.md); shipped product → [02](02-product-context.md); full brief canon → [fact-sheet §0](fact-sheet.md).

**Reference:** https://www.revenuecat.com/for-product/ — fetched live 2026-06-06 (2× WebFetch + WebSearch corroboration + a Chrome-DevTools screenshot pass that captured the image-rendered logo bands).

**Brief canon (`✅ PDF`):** the current page is built on the brief's **4 legacy use cases** (verbatim → [fact-sheet §0](fact-sheet.md) / [02](02-product-context.md)), which the brief calls **"still relevant and important"** (keep, don't discard). The brief also says the page **"is currently stale"** and the product **"has evolved meaningfully… need[ing] a refreshed narrative and positioning."** Everything else here is observed/inferred from the live page.

## Current structure (section-by-section, in order)
1. **Hero** — H1 *"You ship what matters, we handle monetization"* (eyebrow *"For product teams"*); subcopy = stop wasting time on IAP maintenance/data verification, RC handles monetization so teams iterate/analyze/ship. Dual CTA: *Request a demo* / *Explore Product Demo*. Benefit-led but **generic** — "monetization" undifferentiated.
2. **Logo band** — *"Product teams that use RevenueCat:"* — screenshot-confirmed: **Buffer · Notion · VSCO · Zero · Cameo · Goodnotes.** Insight: solid *mid-market consumer* apps, **not** the marquee enterprise/AI brands RC can credibly claim (ChatGPT, Perplexity per BCV) → under-uses its strongest proof. ⚠ Corrects an earlier fact-sheet assumption that "Buffer is gone" — **Buffer is present.**
3. **Core value prop** — H2 *"A solid IAP foundation you can build on"* + **7-item feature grid**: single source of truth · KPI analytics ("15+ metrics") · trigger data-based actions (webhooks) · remote configuration (pricing w/o app updates) · ship what matters (auto-handle Apple/Google API changes) · embrace platform changes · A/B paywall testing. **The page's spine — reads as a feature list, not a narrative.**
4. **Customer testimonial** — single card: mojo.video CTO Francescu Santoni, *"We have gotten back so much time to focus on important features…"* + case-study link. One testimonial, **no quantified outcome**.
5. **Explore the Dashboard** — H2; dashboard as *"command center for in-app purchases,"* spotlights Charts + Customers; CTA *Try the demo*. Interactive product-show — a genuine strength.
6. **Proactively improve your product** — H2; Customer Center · cancellation surveys · retention offers; CTA *Get started*. Retention/churn block.
7. **How it works** — H2; 3-step impl: Configure Products → Connect SDK → Fetch/Subscribe/Unlock. **Dev-onboarding — wrong altitude for a PM.**
8. **How teams use RevenueCat** — H2; 5 persona tiles (Marketing · Data · Product · Support · Engineering). **Dilutes PM focus** — every function equal weight.
9. **Final CTA** — H2 *"Ready to grow?"* + "complete feature suite … free to start." Dual CTA *Start for free* / *Talk to sales*.
10. **Footer** — full nav. Product column lists shipped features that **never appear in the body**: Paywalls, Experiments, Targeting, Charts & analytics, Customer Center, Funnels, Web Billing, Web purchase button, AI agent, Daily payouts. *Build vs. buy* and *Why RevenueCat* also live **only** in the footer.

## Current messaging
- Hero leads with a **benefit promise** ("you ship X, we handle Y"), not the 4 legacy use cases.
- Core H2 frames RC as an **"IAP foundation"** — infrastructure-reliability, **app-store-only**.
- Of the 4 legacy use cases, 3 survive only as **feature bullets**: reduce eng time → "Ship what matters" + "Remote configuration"; single source of truth → present; A/B testing → "A/B paywall testing." The 4th — **reduce multi-platform complexity** — is only implied, no dedicated headline (weakest today).
- **Net:** the 4 use cases are no longer the organizing frame; they're bullets in a 7-item grid. Page leads generic, then enumerates.

## What's stale (gap vs. what shipped) → drives the **add/cut** actions below
- **No Paywalls story** — remote no-code paywall config (most PM-relevant capability) is **footer-only**. Biggest miss.
- **No Web-to-App Funnels** — footer-only; no web→app / web-checkout narrative.
- **No Web Billing** — footer-only; page still frames RC as pure IAP infra ("solid IAP foundation"), outdated now that Web Billing / Web purchase button / Funnels make it cross-surface.
- **Charts undersold** — "15+ metrics" is a spec; omits LTV prediction, paywall-performance charts, REST API → dashboards, not decision intelligence.
- **Experiments undersold** — reduced to "A/B paywall testing"; misses multivariate + predicted-winner-at-significance.
- **Narrative is a feature list** — 7-bullet grid + 5-persona router enumerate instead of telling one PM JTBD arc; "Connect the SDK" is dev-onboarding on a PM page.
- **Thin proof** — one testimonial + logo strip; **no quantified outcomes**; only stat is "15+ metrics" (a spec); no marquee enterprise logos in body.
- **Build-vs-buy invisible** — footer link only; never defeats "we'll build it in-house."
- **Audience dilution** — 5-persona router gives Marketing/Data/Support/Eng equal billing with Product.

## What works (preserve) → drives the **keep** actions below
- **Benefit-led "you ship X, we handle Y" hero** — right instinct; sharpen Y to signal paywalls/experiments/web.
- **Dual-CTA pattern** (self-serve + sales) — serves SMB + enterprise on one page.
- **Logo band placement** under hero — keep; populate with real marquee logos.
- **Interactive "Explore the Dashboard / Try the demo"** — showing the real product is strong for a technical-adjacent PM; expand to Paywalls/Experiments UI.
- **Feature → benefit phrasing** where it exists ("manage pricing without app updates") — apply consistently.
- **Repeated mid-page CTAs** + clean **H2 + short-body + small-feature + CTA** rhythm — scannable; reuse with story-led content.

## Before → After (consolidated keep / cut / add → justifies Track 5 architecture)
Rationale = the stale/works diagnoses above; this is the actionable list.
| Action | Item |
|---|---|
| **keep** | Benefit-led hero (broaden "monetization" → paywalls/experiments/web) |
| **keep** | Dual CTA (Start for free + Talk to sales/Request a demo) |
| **keep** | Logo social-proof band + interactive dashboard demo |
| **keep** | Scannable H2 + short-body + feature + CTA section template |
| **cut** | 7-bullet "IAP foundation" feature grid as the spine (laundry list) |
| **cut** | "How it works" (Configure/Connect SDK/Fetch-Subscribe-Unlock) — dev-onboarding |
| **cut** | 5-persona "How teams use RevenueCat" router — dilutes PM focus |
| **cut** | "IAP foundation" / app-store-only core framing — outdated, now cross-surface |
| **cut** | Single mojo.video testimonial + bare "15+ metrics" as proof — thin/spec |
| **add** | Paywalls (remote, no-code) as a headline PM section |
| **add** | Experiments: multivariate + predicted winner at significance |
| **add** | Expanded Charts: LTV prediction, paywall-performance charts, REST API |
| **add** | Web-to-App Funnels + Web Billing section |
| **add** | Explicit build-vs-buy section answering "we'll build it in-house" |
| **add** | Quantified proof (conversion lift / LTV / revenue / time-saved) + enterprise logos |

**Output / headline diagnosis:** the current page leads generic ("we handle monetization") and enumerates an *IAP-era* feature grid, while the three most PM-relevant shipped capabilities — **Paywalls, Web Billing, Funnels** — and the **build-vs-buy** answer sit in the footer. The refresh promotes those into a story-led, PM-owned, jobs-to-be-done arc with quantified proof.

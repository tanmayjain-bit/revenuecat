# Track 1 — Audience Research (PMs)

**Focus (audience only):** who lands on `/for-product/`, their JTBD, pains, and the question chain the page must answer. Product facts → [02](02-product-context.md); competitive/pricing/build-vs-buy → [03](03-competitive-and-build-vs-buy.md); full brief canon → [fact-sheet §0](fact-sheet.md). Audience canon below is the authoritative slice; where research diverges from the brief, brief wins.

## Brief canon (audience slice, `✅ PDF`)
- Audience = PMs, **enterprise AND SMB** ("accessible and relevant to both ends of the spectrum").
- **JTBD (verbatim):** "Product Managers own user experience and product strategy. They care about aligning monetization with user value, iterating quickly without shipping constant releases, and ensuring pricing, packaging, and access control evolve alongside the product. They are typically not the ones writing billing code, but they are the ones who feel the pain when they cannot move fast."
- Pain→answer mapping (brief canon) = the [Pain → value mapping](#pain--value-mapping-brief-canon) table below.

## Personas
- **Primary — Monetization/Growth PM** (subscription app). Owns pricing, packaging, paywalls, conversion, retention, LTV; measured on conversion / trial-to-paid / ARPU / LTV / churn / ARR. **Doesn't write billing code** — blocked by the eng dependency on every change. Confirmed via live JDs (Headspace Principal PM Subs & Monetization, Hinge Lead PM Monetization, Anthropic PM Monetization, Dynatrace Pricing & Monetization PM): owns pricing/packaging + paywall/purchase-funnel optimization, partners with (≠ personally codes) eng. **Nuance:** senior monetization PMs often own/co-own the experimentation stack + write experiment specs → core friction is **release latency** (every change waits on a release/eng sprint), *not* inability to code; they also influence build-vs-buy architecture while eng implements. Release latency = the velocity + build-vs-buy wedge.
- **Secondary — product/eng leaders & founders** making the build-vs-buy call. Small org = founder wearing the PM hat; large org = PM building the buy-vs-build-in-house business case.

## Jobs-to-be-done (prioritized)
1. Iterate paywalls/pricing/packaging fast — no eng sprint / App Store review.
2. Trust cross-platform monetization data as a single source of truth (iOS/Android/web).
3. Run experiments knowing *long-term* revenue impact, not just short-term conversion.
4. Tie acquisition spend → revenue (campaign→subscription attribution).
5. Open web monetization channels (lower store fees, pre-launch revenue).
6. Insulate from Apple/Google policy churn (pricing rules, refunds).

## Pain points (ranked by intensity)
1. **Eng bottleneck on every change** — paywall change = design + dev + App Store submit + review wait + user update; if it fails the whole cycle resets. #1 emotional pain, sharpest wedge. ([Business of Apps](https://www.businessofapps.com/insights/why-your-paywall-is-your-most-important-growth-lever/), [/for-product/](https://www.revenuecat.com/for-product/))
2. **Slow, uncertain experimentation** — hard to know the real winner and whether short-term lift survives long-term.
3. **Fragmented, untrustworthy cross-platform data** — time lost reconciling instead of acting.
4. **App-store commission** (15–30%) eating margin. *(Precise breakdown → [03](03-competitive-and-build-vs-buy.md).)*
5. **Platform policy volatility & refund abuse** — scrambling to react to Apple/Google changes.
6. **Acquisition→revenue attribution blind spots.**

**Context (anchor):** paywall = **revenue backbone** (RC's defensible framing — avoid "single most important lever," an opinion not a stat) yet the thing PMs can change least independently; that tension is the story. Quantified: hard paywalls ~5× freemium = **10.7% vs 2.1%** median D35 trial-to-paid (*State of Subscription Apps 2026*). Growth polarizing: **top-quartile apps +80%+ MRR YoY, bottom 25% −33%+** (2026). Velocity proxy: top-1000 apps update ~every 2 weeks vs laggards quarterly (42matters/FoxData). *(Dropped as unverified: "top-100 apps ship ~3× more often.")*

## Empathetic intent model (model the PM before the product)
1. **Who's searching:** a monetization/growth PM (or founder-with-hat) who owns subscription revenue but can't ship a paywall change without eng — arrives frustrated post-slow-release or while scoping "build in-house?"
2. **Trying to accomplish:** *instrumental* — run pricing/paywall/experiment changes on their own cadence with trusted data; *emotional* — stop being blocked, own the revenue lever without begging eng for sprint time.
3. **What helps now:** proof they can iterate monetization independently, the full funnel in one platform, and a pre-answered "why not build it ourselves?" with hidden-cost math.
4. **What wastes time:** feature laundry lists, undefined "AI-powered" claims, vague "growth," anything unmeasurable (see Vocabulary).

## Question-Exhaustion Map (page must answer every one)
Chain a PM runs *after* the hero promise; each unanswered = a bounce (to a competitor or to "build in-house"). Track 5 = coverage requirement; Track 6 places objection answers next to the relevant CTA.
- **Immediate (from the thesis):**
  - "Really change paywalls/pricing without an app update?" → remote paywall config, no store review.
  - "Which platforms?" → GA iOS/Android/RN/Flutter/web.
  - "Need engineering at all?" → no-code editor + AI generation; eng does one SDK integration once.
- **Decision-stage:**
  - "Live in days or a quarter?" → speed-to-live proof (SMB) / reliability-at-scale proof (enterprise).
  - "Cost / free tier?" → pricing + free tier (esp. SMB/indie).
  - "Integration/migration effort?" → integration story, SDK once.
- **Objection (this bucket *is* build-vs-buy):**
  - "Why not have eng build paywalls/billing/experiments in-house?" → hidden cost: cross-platform maintenance, store-policy churn, refund handling, analytics plumbing, every change = a release. *(→ 03; page defeats implicitly.)*
  - "Is cross-platform revenue data trustworthy?" → single source of truth.
  - "Breaks when Apple/Google change policy?" → automated refund handling, platform insulation.
  - "Is the A/B 'winner' real or noise?" → predicted 12-month LTV winners.
- **Comparison (triggers a new search):**
  - "Better than Adapty/Superwall/rolling our own?" → completeness (full funnel in one place) + forward-looking LTV. *(→ 03; don't name competitors on the page.)*
- **Edge-case (niche but bounce-worthy):**
  - "Sell on web to dodge the 15–30% cut?" → Web Billing + Web Funnels.
  - "Earn revenue *before* the app launches?" → pre-launch web revenue (Floga proof).
  - "Pull my data into our own dashboards?" → Charts API.

Highest-value entry = the **build-vs-buy objection**; for this audience it's the real competitor.

## Enterprise vs. SMB (must land for both)
- **Enterprise PMs:** reliability at scale (millions of subs), data governance/security, integrations, dedicated support; risk-averse; build-vs-buy = eng opportunity cost. Reassured by marquee logos. ([revenuecat.com](https://www.revenuecat.com/))
- **SMB/indie PMs:** speed-to-live (days not months), free tier, doing more without an eng team (templates, AI generation). Reassured by ease + peer success. ([indies](https://www.revenuecat.com/indies/))
- **Common ground (lead here):** both want to ship monetization without burning eng and to decide pricing from trusted data. Build on common ground; use proof + secondary copy to reassure each end.

## Vocabulary — do / don't
- **Do:** concrete outcomes (conversion, LTV, retention, ARR), quantified claims, time saved, "ship without an app update," "no engineering required," "source of truth," named proof.
- **Don't:** vague "growth"/"synergy"/"revolutionary," unquantified AI hype, jargon without payoff. This audience distrusts unmeasurable claims.

## Pain → value mapping (brief canon)
| PM pain point | RevenueCat answer |
|---|---|
| Eng bottlenecks on paywall changes | Remote paywall config (no app update) |
| Experimentation uncertainty | Predicted 12-month LTV winners |
| Platform policy volatility / refund abuse | Automated Refund Handler |
| One-size-fits-all monetization | Targeting rules engine + Web Funnels branching |
| Acquisition→revenue attribution blind spots | Funnels analytics + UTM + Charts API |
| App-store commission pressure | Web Billing (Stripe, Apple/Google Pay) |
| Late detection of monetization issues | Paywall performance charts + LTV prediction |

## Voice of customer — emotional vs. logical cues
Full quote bank + page implications → [fact-sheet §G-VoC](fact-sheet.md).
- **Emotional cues:** relief ("got my time back"), frustration that billing is undifferentiated grunt work, anxiety about Apple/Google policy churn, fear of silent revenue leaks (skipped transaction listener), distrust of the 1%-of-gross fee, engineer pride/control ("I'll build it myself").
- **Logical cues:** eng opportunity cost, time-to-ship, maintenance burden, lifecycle correctness, control, fees, cross-platform single source of truth, remote iteration speed.
- **Page-safe verbatim anchor:** *"…none of this 'feels' like product building. It's technical overhead. Expensive overhead."* (Stackademic). + jclardy's HN lines + theswiftk.it's "$10K/mo could fund an engineering hire" — the honest at-scale objection to **concede then reframe**.
- ⚠ **Integrity:** Perplexity fabricated several "HN quotes"; verified against live threads, fakes discarded. **Only HIGH-confidence verbatim quotes are page-safe; reconstructed Reddit/G2 lines must NOT appear as testimonials.**

## Primary interview — high-growth PM, ICP (2026-06-06)
First-party discovery interview with a monetization PM at a **high-growth, app-first** company (`✅ 1P` = first-party; treat as a single live data point, not a sample — but it's a *current RevenueCat customer in our exact ICP*, so it carries weight where it confirms desk research). Behavior-first questions; verbatim where quoted.

**Profile:** Owns the whole app, judged primarily on **ARR**. **$11M ARR in 8 months** (genuine high-growth). **iOS + Android only — no web, no interest.** Already a RevenueCat customer. Monetization model = **subscription + consumable credit packs** (hybrid; see new finding below).

**Findings (mapped to wedges):**
- **The eng seam is real and narrow — confirms the "release latency, not inability to code" nuance.** On their credit-packs launch: eng spent **~1 week** wiring new products into entitlements + base targeting params; the PM then spent **~2 weeks** building paywalls (per-scenario), targeting, and experiments *themselves* — and **"once it was shipped I could do it all by myself."** The only eng dependency is *defining new products/entitlements*; day-to-day paywall/targeting/experiment iteration is fully self-serve. → sharpens **velocity/independence** wedge: lead with self-serve iteration, but be honest that net-new product types touch eng once.
- **Forward-looking LTV is the emotional peak, and it's fast.** Decides experiment winners on **predicted LTV (RevenueCat's prediction) + conversion**, and **"got a signal within 1 week."** The single deepest moment in the interview wasn't shipping a paywall — it was **"a win for an experiment within 2-3 days, and it was a win with $$."** → **velocity + forward-looking intelligence collapse into one feeling: validated revenue learning in days, not a quarter.** This is the strongest reframe to surface on the page.
- **Build-vs-buy reframe, in their words:** eng *has* floated building in-house. PM's winning pushback: *"lots of this extra stuff is for free on top of what we'd use for billing/monetisation. We'd honestly use RevenueCat for billing/monetisation, but the fact that it's free and I get to move wayyy faster is such a win."* Build-in-house math: **"another week or 2, so double"** the timeline, pulling eng off roadmap. → reframe = *the differentiating layer (paywalls/experiments/predicted-LTV) is free on top of the billing infra you'd build/buy anyway*; defeats build-in-house on **speed + opportunity cost**, not on "you can't build billing."
- **Source-of-truth proven in behavior:** **"we just look at RevenueCat for both [iOS+Android], I barely look at the platform dashboards."** Apple/Google dashboards go unopened — RevenueCat *is* the dashboard. → strongest behavioral proof yet for the **completeness/source-of-truth** wedge.
- **NEGATIVE finding (what to de-emphasize for this ICP):** app-first, **iOS/Android only, no web path and no interest.** → **Web Billing / Web-to-App Funnels are not a hook for high-growth app-first PMs.** Keep them as edge-case/secondary (still relevant to pre-launch/SMB per Floga), but don't lead with web for this persona.
- **NEW model wrinkle — hybrid subscription + consumable credit packs.** Desk research framed the audience as pure-subscription; this PM runs **subs + credit packs** together, testing structures (e.g., **exit-offer vs. initial paywall**). → monetization isn't only subscription tiers; the page's "pricing/packaging" language should accommodate **consumables/credits**, and RC's per-scenario paywalls + targeting are used exactly this way.
- **Activation insight:** regret was **"I wish we moved with targeting sooner."** Targeting/personalization is high-value-but-underadopted → a possible secondary-CTA / education angle (don't just ship one paywall — target by scenario from day one).

**Page-safe verbatim (1P, paraphrase-attributed — anonymized "a PM at a high-growth app," not a named testimonial):**
- *"It does all the payment stuff, but more than that it's our source of truth for payments — and I can move faster in monetisation as a result."* ← hits all 3 wedges in PM order: billing (table stakes) → source of truth → velocity. Excellent hero-adjacent / closing line.
- *"A win for an experiment within 2-3 days — and it was a win with $$."* ← speed-of-validated-revenue proof.
- *"The fact that it's free and I get to move wayyy faster is such a win."* ← build-vs-buy reframe.
- *"I barely look at the platform dashboards."* ← source-of-truth proof.

⚠ **Integrity:** single first-party interview — directional, not statistically representative. Quotes are real (1P) and page-safe as *anonymized customer voice*; do **not** attribute to a named person/company without permission. Where it confirms desk research (velocity, source-of-truth, predicted-LTV, build-vs-buy), treat as corroboration; where it's net-new (hybrid credits model, no-web ICP), flag as a single-source signal for Track 5 to weigh.

## Sources
- **Primary interview (2026-06-06):** monetization PM, high-growth app-first company, current RC customer (1P; anonymized).
- https://www.revenuecat.com/for-product/ · https://www.revenuecat.com/ · https://www.revenuecat.com/indies/
- https://www.businessofapps.com/insights/why-your-paywall-is-your-most-important-growth-lever/
- https://www.runway.team/blog/best-practices-for-evolving-your-mobile-app-release-process
- https://uxcam.com/blog/top-50-mobile-app-kpis/ · https://www.paddle.com/resources/mobile-app-monetization-guide

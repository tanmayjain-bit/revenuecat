# Landing Page Scaffold — `/for-product/` refresh

**Source of truth for the build.** Section-by-section spec derived from [Track 5](../docs/05-positioning-and-narrative.md) (positioning), [Track 7](../docs/07-proof-and-credibility.md) (proof), [Track 6](../docs/06-conversion-and-cta.md) (CTA placement), and [`design.md`](../design.md) (tokens). Each section lists: **purpose · headline · subhead · body/evidence · proof · CTA · visual.** Copy here is *directional draft* — final copy is wordsmithed in build. Features appear only as evidence for a job (no laundry list).

**Value-prop hierarchy (the spine):**
- **Primary (umbrella):** *Drive revenue at product speed* — run monetization on your own cadence.
- **Secondary (in order):** 1. Velocity — *Move your revenue, not your roadmap* · 2. Source of truth — *Quote every figure with confidence* · 3. Forward-looking — *Know the 12-month winner in week one* · 4. Build-vs-buy — *Keep the upside, skip the plumbing*.

**Audience:** Monetization/Growth PM, enterprise + SMB. **Voice:** verb-first, "you"-led, concrete → quantified. Lead emotional (relief), close logical (the number).

---

## 1. Nav
- Logo · (minimal links) · **Start for free** (primary btn) · **Talk to sales** (ghost/secondary).
- Sticky, white bg, ink-navy text. Indigo CTA pill.

## 2. Hero — *primary value prop, velocity-led*
- **Purpose:** land the primary value prop + relief in one screen.
- **H1:** Drive revenue at product speed.
- **Subhead:** Move your revenue, not your roadmap — change pricing, paywalls, and packaging on your cadence, no app release, no store review.
- **CTA:** Start for free · Talk to sales.
- **Proof teaser:** one-line trust ("Powers ~1/3 of all new subscription apps" — BCV framing) OR inline stat.
- **Visual:** signature icon-coin → dotted line → RC-hexagon flow (ad → funnel → checkout → redemption), or a paywall-config-without-release motion still. White bg, generous whitespace.

## 3. Logo band (social proof, immediate)
- **Purpose:** peer-trust de-risk above the fold-ish.
- **Logos:** marquee tier — OpenAI/ChatGPT, Notion + named-quote logos (VSCO, Runna, Ladder, ElevenLabs). Pull *up* from the current page's mid-market set.
- **Visual:** quiet grayscale logo strip. No metric needed here.

## 4. Problem / tension
- **Purpose:** name the PM's core pain so they feel seen.
- **Headline:** You own the revenue number — but you can change the lever least independently. *(refine)*
- **Body:** Every paywall / price / packaging move waits on a release: design → dev → store submit → review → user update. Fewer shots on goal, and they land weeks late.
- **Proof:** Your paywall is the revenue backbone — yet it's the thing you touch last. Stakes: top-quartile apps grew **MRR 80%+ YoY** while the bottom 25% **shrank 33%+**. Speed is the gap.
- **Visual:** before/after or a stalled "release train" motif.

## 5. The shift (insight bridge)
- **Purpose:** pivot from pain to the new world; set up the 3 pillars.
- **Headline:** Monetization just got off the release train. *(refine)*
- **Body:** What used to be an eng ticket is now something you operate directly. Three things change → (transition into pillars).
- **Visual:** light, optional — could be a 3-up teaser of the pillars.

## 6. Pillar 1 — VELOCITY *(secondary #1, the freedom to move)*
- **Headline:** Move your revenue, not your roadmap.
- **Subhead:** Own conversion, ARPU, churn, ARR — and actually move them, at your cadence, without spending eng's roadmap.
- **Evidence (feature → benefit → job):** remote no-code **Paywalls** (AI generation, Figma export, GA iOS/Android/RN/Flutter/web) · **Web-to-App Funnels** · **Targeting** rules. Reassurance line: *eng integrates the SDK once; day-to-day iteration is yours.*
- **Proof:** **Pixelcut +16% paying customers from one A/B test** ("this test alone paid for all of RevenueCat's costs") · **Floga: six figures in a single day before launch** · pull-quote: *"a win for an experiment within 2–3 days — and it was a win with $$."*
- **CTA:** inline Start for free.
- **Visual:** paywall editor / drag-drop; two-up alternating layout.

## 7. Pillar 2 — SOURCE OF TRUTH *(secondary #2, the confidence to quote a figure)*
- **Headline:** Quote every figure with confidence.
- **Subhead:** One reconciled revenue truth across iOS, Android, and web — refunds, grace periods, retries, and restores already accounted for. RevenueCat *is* the dashboard.
- **Evidence:** entitlement substrate (cross-platform + **Web Billing** + Redemption Links) · **Automated Refund Handler** · **Charts + Charts API** · **40+ integrations** (Amplitude, Mixpanel, AppsFlyer, Adjust, Braze, BigQuery, Snowflake…) · Rico.
- **Proof:** **40+ named integrations** band (the concrete proof of "feeds your whole stack") · pull-quote: *"I barely look at the platform dashboards."* · implicit wedge: *paywalls are the surface; entitlements are the source of truth.*
- **Visual:** "one truth → many tools" hub-and-spoke; integration logo grid. (SOC2/GDPR enterprise reassurance lives in the §10 trust band, not here.)

## 8. Pillar 3 — FORWARD-LOOKING *(secondary #3, the conviction to bet early)*
- **Headline:** Know the 12-month winner in week one.
- **Subhead:** Don't optimize for a short-term conversion bump that churns — pick the variant with the best *predicted long-term LTV*, mid-experiment.
- **Evidence:** **Experiments** (multivariate A/B/C/D + **predicted 12-month LTV winners** + one-action rollout) · **LTV Prediction + Cohort Explorer** · 4 real-time **paywall-performance charts**.
- **Proof:** predicted-LTV winner surfaced while the test is still running (the brief's "predict long-term revenue impact, not just short-term conversion") · **55% of 3-day-trial cancels happen Day 0** (lagging data finds it too late) · PM-voice: *"a win for an experiment within 2–3 days — and it was a win with $$."*
- **Visual:** experiment results with a "predicted winner" badge surfaced mid-run.

## 9. Build-vs-buy *(secondary #4, the focus to build product)*
- **Purpose:** defeat "we'll build it in-house" — the real competitor. Concede → reframe.
- **Headline:** Keep the upside, skip the plumbing. *(working line: "We could build this ourselves." Sure — the easy 20%.)*
- **Concede (honest):** the client SDK is a couple of HTTP calls; the 1% fee is real (*"could fund an engineering hire"*).
- **Reframe (correctness checklist):** grace periods = "three different truths," `originalTransactionId` "stable until it isn't," can't be tested in sandbox — then build it **twice** (Android, web) and maintain it forever against policy churn. The differentiating layer (paywalls/experiments/predicted-LTV) is **free on top of the billing infra you'd build anyway**.
- **Proof:** Floga CTO *"it would have taken us 3x the time to build this ourselves"* · PM voice: *"another week or 2, so double… the fact that it's free and I get to move wayyy faster is such a win."*
- **CTA:** Start for free (objection-adjacent, per Track 6). Note free-tier ($0 to $2.5K MTR) here for SMB.
- **Visual:** iceberg / "the part you see vs. the part you maintain."

## 10. Scale & trust band
- **Purpose:** trusted-at-every-scale de-risk (indie → enterprise).
- **Headline:** Trusted at every scale.
- **Body:** Lead with third-party framing — **"Powers ~1/3 of all new subscription apps"** (BCV). Secondary, framed as RevenueCat-reported: 106K apps · $14B+ processed annually · 3B+ API requests/day · 4.8/5 G2 & Capterra · SOC 2 · GDPR.
- **Proof:** OpenAI/ChatGPT (*"we never had to slow down"*) + Notion named-exec quotes.
- **Visual:** stat row (coral key numbers) + marquee logos.

## 11. Close / final CTA
- **Purpose:** emotional→logical close, drive the primary action.
- **Headline:** Drive revenue at product speed. *(echoes the primary value prop to close the loop)*
- **Synthesis line:** *"It does all the payment stuff, but more than that it's our source of truth for payments — and I can move faster in monetisation as a result."* (anonymized PM voice — all the value props in one line).
- **CTA:** Start for free · Talk to sales.

## 12. Footer
- Minimal: product/company/legal columns, RC hexagon. Not load-bearing.

---

## Build notes
- **Tokens / fonts / components:** [`design.md`](../design.md) — ink-navy base, indigo CTA, coral key stats/highlight, green positive signals; full-pill buttons; 16px soft cards (purple-tinted shadow); LIGHT headings (500 display / 400 sub-heads); two-up alternating sections; homepage motion (logo marquee + scroll-reveal).
- **Stack:** single static page + Tailwind, no framework, deploy to Vercel ([Track 8.5](../docs/08-5-tech-stack.md)).
- **Honesty guardrails:** no Buffer/Dipsea/Holywater logos; don't mix 106K/$14B with 115K/$16B; never promise a specific app a benchmark result; don't name competitors.
- **Cut (do not add):** 5-persona router · "Connect the SDK" dev section · IAP-era 7-bullet grid · Daily payouts · web as a lead · full integration list.

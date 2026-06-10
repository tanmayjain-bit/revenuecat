# Deep Fact Sheet — RevenueCat "For Product" page

**Purpose:** The consolidated, source-tagged evidence base for Track 5 synthesis — a human-review checkpoint before any positioning is written. Distilled from [Track 1 (audience)](01-audience-research.md), [Track 2 (product)](02-product-context.md), [Track 3 (competitive)](03-competitive-and-build-vs-buy.md), [Track 4 (teardown)](04-current-page-teardown.md), and [Track 7 (proof)](07-proof-and-credibility.md); see those docs for full per-claim sourcing.

> **Research note (2026-06-06):** This sheet consolidates everything from the research tracks, with Perplexity MCP corrections folded in: the in-house build-cost estimate corrected upward, **no third party independently verifies RC's scale claims**, the audience/demand-side stats hardened, the Track 4 teardown executed live, the competitive set deepened around **Superwall** + app-payments/product-growth adjacencies, **voice-of-customer** quotes gathered (§G-VoC, emotional vs logical cues), and the product picture complemented (§I — Rico AI agent, Daily payouts, Customer Center, 40+ integrations). The `/for-product/` logo band was screenshot-confirmed (Buffer correction, §B). **Scope (per Track 3):** the competitive set is **Adapty · Superwall · build-in-house** — Stripe and Paddle are *not* competitors for this audience (they're web-only and partly RC complements) and are de-scoped; **build-in-house is the named competitor that matters** (deep analysis §E).
>
> ⚠ **Integrity flag:** Perplexity fabricated several "verbatim" Hacker News quotes during VoC research; they were verified against the live threads, found not to exist, and everything unverifiable was down-graded. **Only the HIGH-confidence verbatim quotes below are page-safe — never ship the LOW/reconstructed ones as testimonials.**
>
> **Confidence legend:** **✅ PDF = stated in the brief (the source of truth — treat as 100% authoritative; the reviewer indexes against this).** HIGH = primary + recent (web) · MEDIUM = reputable secondary / vendor self-report without disclosed methodology · LOW = undated/soft. VENDOR = RevenueCat's own marketing (motivated source). `(inferred)` = reasoned, not directly sourced.
>
> **How to read this sheet:** **§0 (below) is the brief canon — everything in it is `✅ PDF` and must never be contradicted by anything later in this doc.** Sections A–J are *supporting research* (web/vendor/inferred) that enrich the canon; where any of them touch a brief claim it carries a `✅ PDF` tag, and where research and brief ever diverge, **the brief wins.**

---

## §0. Brief canon — the PDF source of truth (`✅ PDF`, do not contradict)
*Verbatim from `Take-Home Assignment - PMM at RevenueCat.pdf`. This is the tier the reviewer treats as 100% correct. Quotes are exact; "key insight" lines are the brief's own framing and are the safest possible on-page claims.*

**The task & guardrails (pp.1):** **"vibe-code"** an updated `/for-product/` page (currently *"stale"*) with **Product Managers as the primary audience**, merging old + new into *"a complete monetization solution for PMs."* *"Balance relevant feature education with the overall value and jobs-to-be-done… for a Product Manager."* Explicit warning (twice): **"We do not want you to create a laundry list of features or reflect all the features"** — *"use your discretion to organize and share what feels most important and compelling to lead the reader to action."* Synthesize, don't enumerate.

**The 4 legacy use cases — "still relevant and important" (keep, don't discard):**
1. *"Reduce engineering time spent on maintenance & monetization changes"*
2. *"Reduce the complexity of supporting multiple platforms"*
3. *"Maintain a single 'source of truth' of monetization data and reporting"*
4. *"Improve conversion by A/B testing with pricing, packaging, and paywalls"*

**The 5 "What's New" product areas — each with the brief's own key-insight line (the safest on-page claims):**
- **Paywalls** — remotely configure the *entire* paywall view **"without any code changes or app updates"**; visual drag-and-drop (templates or blank canvas); recent: **AI-powered paywall generation, custom variables (personalize copy at runtime via SDK), Figma export, full branding system**; **GA across iOS, Android, React Native, Flutter, and web.** → *Key insight: "paywall iteration no longer requires a designer, engineering sprint or an App Store review cycle."*
- **Web-to-App Funnels** — no-code visual editor; multi-step screens, branching logic (URL params / survey answers / country), connect a web checkout **(RevenueCat Billing or Paddle)**, publish to a hosted URL, **all without touching engineering**; end-user flow = ad → personalized onboarding → web checkout → **Redemption Link** → app downloaded with subscription **already active**; built-in per-step conversion/drop-off analytics + **UTM tracking**. → *Key insight: "capture, qualify, and convert users before they ever touch the App Store, improving attribution, reducing platform fees, and enabling faster experimentation."*
- **Charts** — **LTV Prediction + Cohort Explorer** (Revenue / Realized LTV / Retained Subscriptions by cohort & period; **trials now included in LTV predictions**); **four new real-time Paywall Performance charts** (encounter rate, conversion rate, LTV by paywall, abandonment); **Charts API** (programmatic access to all subscription analytics → custom dashboards / automated reports / AI pipelines); **Apple Search Ads segmentation** (by ASA keyword or claim type). → *Key insight: "Charts are the analytical layer that connects paywall decisions, experiment results, and acquisition spend to actual business outcomes."*
- **Web Billing (RevenueCat Billing)** — web purchases that work seamlessly with mobile: hosted **Web Paywall Links** or **Web SDK**, **Stripe integration, Apple Pay & Google Pay, multi-currency, introductory pricing, self-serve upgrades in the customer portal**; web purchases auto-unlock in-app entitlements via **Redemption Links**. → *Key insight: "Web Billing unlocks a monetization channel that bypasses app store commissions (typically 15-30%), gives full pricing flexibility, and enables pre-launch revenue. For example, Floga generated six figures in revenue in a single day before their app was live."*
- **Experiments** — controlled A/B tests on paywalls, pricing, packaging: **multivariate A/B/C/D** (up to four variants); **predicted 12-month LTV winners** (calculates expected 12-mo LTV per variant, surfaces the predicted revenue winner *while the experiment is still running*); **one-action winner rollout** (stop + auto-update offering or create a targeting rule in one click); **draft mode**. → *Key insight: "Experiments are no longer just about short-term conversion rates. You can now predict long-term revenue impact and ship winners faster, with less manual work."*

**Audience — PMs (pp.4, authoritative):** the page serves **both enterprise and SMB** PMs. **JTBD (verbatim):** *"Product Managers own user experience and product strategy. They care about aligning monetization with user value, iterating quickly without shipping constant releases, and ensuring pricing, packaging, and access control evolve alongside the product. They are typically not the ones writing billing code, but they are the ones who feel the pain when they cannot move fast."*

**Pain-point → RevenueCat answer (the brief's own mapping — use these pairings exactly):**

| Pain point (`✅ PDF`) | How RevenueCat addresses it (`✅ PDF`) |
|---|---|
| Engineering bottlenecks on paywall changes | Remote paywall configuration via **Paywalls** (no app update required) |
| Experimentation uncertainty | **Predicted 12-month LTV winners** in Experiments |
| Platform policy volatility and refund abuse | **Automated Refund Handler** |
| One-size-fits-all monetization | **Targeting rules engine** + **Web Funnels** with branching logic |
| Blind spots in acquisition-to-revenue attribution | **Funnels analytics** (UTM) + **Charts API** |
| App store commission pressure | **Web Billing** with Stripe, Apple Pay, Google Pay |
| Late detection of monetization issues | **Paywall performance charts** + **LTV prediction** |

**Evaluation criteria (what's graded, pp.5–6):** Visual Storytelling (feel *"RevenueCat-ish,"* not pixel-perfect) · Messaging/Positioning/Narrative (*"synthesize the features into a unified story rather than a feature list"*; strong information hierarchy translating features → PM value/JTBD) · **"Confident assumptions backed by reasoning… Avoid spiraling on 'being right.'"** · Use of AI (clear explanation, evidence of iteration/pivots). **Constraints:** no no-code site builders (Squarespace/Wix/Webflow); original work; no outsourcing; AI-assisted tools required.

**Deliverables & logistics (pp.5, `✅ PDF` — logistics, not positioning):** (1) a **functional, deployable** vibe-coded page targeting PMs; (2) a **separate doc on AI process + assumptions** (any format — doc/Notion/Loom — covering research, ideation, iteration, tool usage → *this repo's `docs/` + Track 0 is that deliverable*). Share via **live link** (Vercel/Netlify/built-in) **or project link** (Replit/Bolt/v0). Recommended tools: v0, Bolt.new, Replit Agent, Cursor/Copilot, ChatGPT/Claude/Gemini. **$30 tool-credit stipend.** ~4–6 hour budget.

> ⚠ **Note on Floga:** the brief says **"six figures … in a single day before their app was live"** (`✅ PDF`). The specific **"$120,000+"** figure in §B is from RevenueCat's case-study page (web/VENDOR), not the brief — when in doubt on-page, use the brief's "six figures."

---

## A. RevenueCat scale — credibility anchors
All vendor-published (RevenueCat reporting on itself); HIGH that they state it, no third-party audit.

- **106,000 apps · $14B+ processed/yr · 3B+ API requests/day** (revenuecat.com homepage).
- Report dataset is larger: **115K apps / $16B / 1B+ transactions** (*State of Subscription Apps*, 2025 data). **Do not mix the two pairs** on the page — use the homepage pair as the live self-description; reserve the report pair for report-citation context.
- 4.8/5 G2 & Capterra · SOC 2 · GDPR.
- ⚠ **No third party independently *verifies* any of these numbers** (confirmed 2026-06-06). SaaStr, Subscription Insider, Bain Capital Ventures, and The SaaS News all *attribute* the figures to RevenueCat — none audited them. **Frame as "RevenueCat-reported."**
- ✅ **Stronger-than-the-raw-totals credibility play:** Bain Capital Ventures (investor, third party) states RevenueCat *"powers over one-third of all new subscription apps worldwide"* and names ChatGPT, Notion, Perplexity as customers. This third-party-acknowledged market-share framing + marquee brands reads as more credible than self-reported $/app totals — **lead the scale story with it.** ([BCV](https://baincapitalventures.com/))

## B. Customer proof — de-riskers
- **Floga — `✅ PDF` "six figures in revenue in a single day before their app was live"** (the brief's own Web Billing proof point; doubles as the build-vs-buy killer). The specific **"$120,000+"** figure + CTO Madson Cardoso's *"it would have taken us 3x the time if we needed to build this ourselves"* are from the case-study page (web, **HIGH**, but VENDOR). **On-page, prefer the brief's "six figures."** ([floga](https://www.revenuecat.com/customers/floga))
- **Pixelcut — +16% paying customers from one weekly-vs-monthly A/B test**; co-founder: *"this A/B test alone paid for all of RevenueCat's costs."* **MED-HIGH** (named exec, specific test). ([pixelcut](https://www.revenuecat.com/customers/pixelcut))
- ElevenLabs **$1M ARR in 16 days** · VSCO **~5% churn reduction** · Runna **30x YoY** · RocketSim **+47% LTV** · Ladder **0→100K subs** — **MEDIUM**; headline metrics, baselines/definitions unconfirmed.
- **Marquee logos RC uses elsewhere (homepage / case studies):** Notion, OpenAI/ChatGPT, VSCO, Photoroom, ElevenLabs, Runna, Ladder, Opal, Widgetsmith, Pixelcut, +more.
- **The live `/for-product/` logo band specifically (screenshot-confirmed 2026-06-06): Buffer · Notion · VSCO · Zero · Cameo · Goodnotes.** These are mid-market consumer apps — the current page **under-uses** RC's strongest enterprise/AI logos. The refresh should pull in the marquee tier.
- ✅ **Correction:** an earlier note here claimed "Buffer is gone — do not use it." That was wrong (the prior fetch couldn't read image-based logos). **Buffer IS on the live page** and is safe to display.

## C. Industry benchmarks — make claims concrete (not generic filler)
From RevenueCat's *State of Subscription Apps* (2025 data, 115K-app dataset). HIGH the report states these; MEDIUM that any single benchmark transfers to a given app. ([report](https://www.revenuecat.com/state-of-subscription-apps/))

| Benchmark | Figure | Backs the claim |
|---|---|---|
| Paywall strategy moves revenue | Hard paywall **10.7% (D35)** vs **2.1%** freemium (~5x); RPI D60 **$3.09 vs $0.38** | "Your paywall *is* the lever — you must be able to test/change it fast." |
| Trial length matters | 17–32d trials **42.5%** vs ≤4d **25.5%**; **55% of 3-day-trial cancels happen Day 0** | "Packaging/trial decisions are high-leverage → experiment, don't guess." |
| Geography shifts LTV | LTV **$32 NA vs $14 IN/SEA** | "Segments differ — target offers by audience." |

⚠ Category-level — never promise a specific app's result.

## D. Competitive landscape
**Competitive set = Adapty · Superwall · build-in-house.** Stripe/Paddle are web-only and partly RC complements (RC Web Billing uses Stripe; Web Funnels can use Paddle) → not competitors for this audience; de-scoped. Pricing (all HIGH/primary):

| Product | Free tier | Then | Charges on |
|---|---|---|---|
| **RevenueCat** | $2,500 MTR/mo | 1% | all tracked revenue |
| **Adapty** | $5,000 MRR/mo | 1% | all tracked revenue |
| **Superwall** | $10,000 MAR/mo | 1% (+ optional $49/$199 plan fees) | paywall-attributed revenue only |
| **Build in-house** (StoreKit / Google Play Billing) | — | $0 SDK fee | but 15–30% store commission applies regardless |

> **Pricing verified 2026-06-06 against primary pages.** Terminology fix: Superwall's **MAR = "Monthly *Attributed* Revenue"** (not "Active"). RC has the **lowest** free-tier entry of the three IAP-billing rivals ($2.5K vs Adapty $5K vs Superwall $10K) — all then 1%.

- **Where RC honestly loses:** lowest free tier ($2.5K) — an early app pays RC *first*; Adapty is cheaper longer; Superwall is best-in-class at pure paywall iteration.
- **Where RC wins:** every rival is **partial** — Superwall = paywalls only (no billing/entitlement backend), build-in-house/native = backend only (you own all the correctness + maintenance). RC is the only full stack + forward-looking LTV.
- **Build-in-house is the named competitor that matters** for this audience — full cost/correctness analysis in §E.
- **Positioning reminder:** do NOT name competitors on the page — this sharpens our own wedges.

### Superwall has moved upmarket — the key 2026 competitive finding
Superwall (the strongest product-growth/paywall player) has **re-positioned from "paywall tool" to "platform / source of truth,"** colliding head-on with RC's positioning:
- Its PM page (superwall.com/solutions/by-team/product-managers) now headlines *"The central engine for subscription product growth"* and claims *"Superwall is the single source of truth for your subscription product."* Homepage: *"The paywall experimentation platform for mobile apps … in 2 lines of code."* Self-reported "90% less time to experiment / 20–30% revenue growth" (VENDOR). **HIGH** they say it.
- **But its own docs route billing/product definition "through RevenueCat,"** its web checkout is a Stripe deep-link that unlocks entitlements *in your app*, and it bills only on **Monthly *Attributed* Revenue** — i.e. it is **not** the billing/entitlement source of truth. Its "source of truth" = subscription *strategy + paywall metrics*, **not** billing state. ([superwall.com/docs](https://superwall.com/docs) · PRIMARY · HIGH)
- **RC wedge (use implicitly, never name them):** *"Paywalls are the surface; entitlements are the source of truth."* Teams run Superwall **on top of** a RevenueCat backend — so the message isn't "beat the paywall tool," it's *own the substrate that every paywall/analytics/attribution tool plugs into*. RC also ships its own remote Paywalls + Experiments (with predicted-LTV winners), so a team gets surface velocity **and** the billing backend in one platform. Counter their "single source of truth" claim by owning the only definition that includes billing, receipts, refunds, grace periods, and cross-platform entitlements.

### Broadened map — rivals vs. complements (all verified 2026-06-06)
- **Direct subscription-infra rivals:** Adapty (closest; cheaper longer), Qonversion (**still active — did NOT shut down**; quote-based), Nami ML (ML paywall personalization), Purchasely (design-led, EU-strong, multi-store). RC wins on scale, forward-looking LTV, and breadth.
- **Consolidation signal:** RC **acquired Glassfy (2023)** and sunset it (an RC consolidation proof point); Stripe **acquired Lemon Squeezy (2024, PRESS)** on the web-payments side. The category is consolidating around RC.
- **Complements, NOT rivals (they consume RC's data):** Amplitude / Mixpanel (product analytics & experiment layers), AppsFlyer / Adjust / Branch (MMPs) — all ingest RC's server-side renewal/cancel/refund events to keep LTV/ROAS accurate (critical under SKAdNetwork); none validate receipts or own subscription state. **Reframe these as "RC is the source of truth that feeds your stack," not threats.**
- **Native price experiments are limited:** Apple PPO / Custom Product Pages + Play store-listing tests only A/B **store-listing assets** (icons/screenshots), not in-app paywall UI — in-app variant changes still need a build + review. This is exactly the gap RC's server-side remote paywalls/experiments fill.
- **Separating axes (where RC sits):** (1) point-tool vs full platform · (2) mobile-IAP vs web vs cross-surface · (3) lagging conversion vs forward-looking LTV · (4) paywall-surface vs source-of-truth. RC is the **source-of-truth substrate that also ships the surface** — the defensible intersection.

## E. Build-vs-buy — the real competitor (strongest framing)
The sharpest angle is **correctness, not the happy path**:

- **Pratilipi engineering write-up** (first-hand, non-vendor) — **HIGH** for the edge cases existing: `originalTransactionId` is "stable until it isn't" (new IDs after account/country changes → multiple active IDs); the only reliable user token (`appAccountToken`) can be missing and isn't guaranteed; naive active/inactive modeling caused them to revoke access too early / extend too long.
- **Apple's own docs** — **HIGH**: grace periods (3/16/28 days) = "three different truths"; billing retries up to 60 days; **grace periods can't be tested in sandbox** — some failure paths can't be QA'd before prod; idempotency keyed differently per event type.
- **"Build it twice"** — all of the above must be rebuilt for Google Play (different API/lifecycle), then web. `(inferred, structurally sound)`
- **Quantified cost (corrected upward 2026-06-06):** the prior ~2–4 week / $12K–24K indie-blog figure is **too low**. Best non-vendor anchor — **Abbacus Technologies**: an intermediate subscription-billing system runs **$200K–$500K over 6–9 months + 15–25%/yr maintenance**; the mobile-IAP "core engine" slice (~30–50%) implies roughly **$60K–$250K / 2–9 engineer-months** (**SECONDARY/MED**). **Page guidance:** frame in-house as *"months of engineering + a permanent maintenance tax,"* **not** a single hard dollar number — no PRIMARY source nails the exact mobile-IAP scope.
- **PM-specific drag:** in-house couples every paywall/price change to an eng ticket + store-review cycle (grounded in the brief-verified Paywalls claim — defensible without a stat).
- Customer-attested: **Floga CTO — "3x the time" in-house** (VENDOR but customer quote).
- **Buyer-side corroboration (`✅ 1P` interview):** an ICP PM whose eng team *did* float building in-house estimated it would **"double" the timeline** ("another week or 2"), and the winning pushback was opportunity-cost, not capability — *"we'd honestly use RevenueCat for billing/monetisation, but the fact that it's free and I get to move wayyy faster is such a win."* → the **PM-voice** echo of Floga's "3x": reframe build-in-house as *the differentiating layer (paywalls/experiments/predicted-LTV) is free on top of the billing infra you'd build anyway* — defeat it on speed + opportunity cost, not "you can't build billing."

## F. Differentiation wedges (both research passes converged here)
1. **Velocity / independence — "ship monetization without shipping code"** — lead with this; it defeats build-in-house and rests on a brief-verified product claim.
2. **Completeness / source-of-truth — "paywalls are the surface; entitlements are the source of truth."** Every rival is partial, and the strongest one (Superwall) now *claims* "source of truth" while routing billing through a backend like RC's. Own the only definition of source-of-truth that includes billing, receipts, refunds, grace periods, and cross-platform/web entitlements — the substrate every paywall, analytics, and attribution tool plugs into. This simultaneously defeats "stitch point tools together," "build the connective tissue ourselves," and the upmarket-paywall-tool pitch.
3. **Forward-looking intelligence — predicted LTV, not lagging conversion** — clearest substance win over Adapty/Superwall.

## G. Audience & demand-side — the pain the page rests on
From [Track 1](01-audience-research.md), hardened 2026-06-06 (Perplexity + live JDs + *State of Subscription Apps 2026*).

- **Persona (HIGH, JD-corroborated):** a Monetization/Growth PM who owns pricing, packaging, paywalls, conversion, ARPU, churn, LTV — and *partners with* engineering rather than writing billing code. Verified against live JDs: Headspace, Hinge, Anthropic, Dynatrace. **Key nuance for copy:** the friction isn't "can't code" — senior monetization PMs often own the experiment stack and write specs. It's **release latency**: every paywall/price/packaging change waits on an app release + store-review cycle. *That latency is the velocity + build-vs-buy wedge.*
- **Paywall framing (use this wording):** the paywall is the **"revenue backbone"** (RevenueCat's own defensible phrase) — **not** "the single most important lever" (that's opinion, invites pushback). Quantified backing: **hard paywalls convert ~5× freemium — 10.7% vs 2.1% median D35 trial-to-paid** (report).
- **Velocity = winning (HIGH):** growth is concentrating at the top — **top-quartile apps grew MRR 80%+ YoY while the bottom 25% shrank 33%+** (~113-pt gap, report). Cadence corroboration: **top-1000 App Store apps update ~every 2 weeks; 74–75% update at least monthly** (42matters via FoxData, SECONDARY). *⚠ The earlier "top-100 ship 3× more often" stat is UNVERIFIED — do not use it; use these instead.*
- **Urgency stat:** **55.4% of all 3-day-trial cancellations happen on Day 0** — onboarding/paywall timing is a live, PM-owned pain (report).
- **App-store fee precision (HIGH, primary):** Apple **30% standard / 15% Small Business Program** (≤$1M *proceeds*, net not gross) · auto-renewable subs 30% yr 1 then **15% after one year**. Google Play **15% on first $1M/yr, 30% above** (one-time/IAP) · **subscriptions 15% from day one.** Use "15–30%" as the honest range.

### G-VoC. Voice of customer — emotional vs. logical cues
From [Track 1](01-audience-research.md) voice-of-customer research (Reddit/X/LinkedIn/HN/blogs). **Cues drive copy; only the HIGH-confidence verbatim quotes are page-safe.**

**Emotional cues** (lead the hero/story with these): **relief** — "got my time back," ripping out hand-rolled StoreKit code · **frustration** — billing is undifferentiated grunt work that "doesn't feel like building product" · **anxiety** — Apple/Google policy churn breaks in-house logic (2026 Guideline 3.1.2 paywall rejections) · **fear of silent revenue leaks** — the background transaction listener "many tutorials skip" is where renewals/refunds fail unnoticed · **distrust** — the 1%-of-gross fee on top of Apple's 30% ("could fund an engineering hire") · **pride/control** — "receipt validation is just a couple HTTP calls, I'll build it myself."

**Logical cues** (the build-vs-buy section): engineering opportunity cost · time-to-ship (hours vs weeks/months) · maintenance burden as APIs change · correctness across the full lifecycle checklist (initial purchase, renewal, billing retry, refunds, trials, intro offers, upgrade/downgrade, S2S notifications, cross-platform restore) · control/independence · the 1% fee · cross-platform single source of truth · remote monetization-iteration speed.

**HIGH-confidence verbatim quotes (page-safe pull-quotes):**
- *"Subscription logic, cross-platform billing rules, receipt validation, entitlements, refunds — none of this 'feels' like product building. It's technical overhead. Expensive overhead."* — React Native/Expo dev, Stackademic ([src](https://blog.stackademic.com/why-revenuecat-became-my-go-to-subscription-engine-for-react-native-expo-apps-1eb75a85fef0)). **The strongest single anchor for the page.**
- *"StoreKit sucks."* / *"you have to run your own backend purchase server because there is a ton of subscription information that is only relayed to the server"* / *"Services like RevenueCat help small devs deal with this, but then you have another cut out of your paycheck"* — jclardy, [HN 28486160](https://news.ycombinator.com/item?id=28486160).
- *"This is the piece many tutorials skip — and it is critical. You need a long-running task that listens for transaction updates… when a subscription renews in the background… or when a refund is processed."* — theswiftk.it editorial (the silent-failure correctness point).
- *"At 100K subscribers with $10/month ARPU, RevenueCat's 1% fee … is $10,000/month. StoreKit 2 is free. That difference can fund an entire engineering hire."* — theswiftk.it (**the honest at-scale objection to concede then reframe**).

**MEDIUM:** YouTube indie-vlog "ripped out all my StoreKit 2 code and replaced it with RevenueCat" + costbench-aggregated fee/feature-gating complaints. **LOW / reconstructed (do NOT put on the page as testimonials):** the r/iOSProgramming and G2 "sentiment" lines — copy-shaping only.

**⭐ First-party PM voice (`✅ 1P`, 2026-06-06 interview — fills the gap: everything above is *developer* voice; these are the *buyer/PM* voice the page actually targets).** One ICP interview (high-growth app-first co., current RC customer, owns ARR) — directional not representative, but page-safe as *anonymized customer voice* (don't attribute to a named person/company). All three wedges land in the PM's own words, in PM priority order:
- *"It does all the payment stuff, but more than that it's our source of truth for payments — and I can move faster in monetisation as a result."* → **the cleanest one-line statement of all 3 wedges** (billing = table stakes → source of truth → velocity); strong hero-adjacent / closing candidate.
- *"I barely look at the platform dashboards."* → source-of-truth **proven in behavior** — Apple/Google dashboards go unopened, RC *is* the dashboard. (Behavioral proof the §G-VoC dev quotes don't give.)
- *"A win for an experiment within 2-3 days — and it was a win with \$\$."* → predicted-LTV velocity made concrete; note the **emotional peak was the fast validated-revenue win, not "shipping without eng."** Lead the Experiments story with *speed-to-a-revenue-answer*, not just "multivariate testing."
- *"The fact that it's free and I get to move wayyy faster is such a win."* → build-vs-buy reframe (see §E).
- ⚠ Net-new single-source signals (flag for Track 5, don't treat as canon): hybrid **subscription + consumable credit-packs** model (monetization ≠ only sub tiers — "pricing/packaging" copy should accommodate consumables); and this app-first ICP was **iOS/Android-only with zero web interest** (one data point — does *not* override the brief's Web Billing area, but suggests **not leading with web** for the high-growth app-first PM).

**Page implications:** lead with the relief + opportunity-cost frame ("stop owning billing infrastructure that doesn't move your product forward"); build an explicit build-vs-buy section that **concedes the fee/"I could build it" point honestly, then reframes** via the lifecycle checklist (client SDK is a fraction of the real work); give monetization-iteration its own PM-owned section; address the 1% fee **proactively** near the CTA (lean on free-to-$2.5K-MTR for SMB); split altitude — SMB = speed/relief/free tier, enterprise = reliability/correctness/cross-platform truth.

## H. Current-page gap — the before→after the refresh must execute
From [Track 4](04-current-page-teardown.md), live-fetched 2026-06-06. **The single sharpest finding:** the live page leads generic (*"You ship what matters, we handle monetization"* / *"A solid IAP foundation"*) and enumerates an **IAP-era 7-bullet feature grid + a 5-persona router** — while the three most PM-relevant shipped capabilities and the build-vs-buy answer sit **in the footer**.

- **Buried in the footer (must promote to the body):** **Paywalls** (remote, no-code — the #1 PM capability), **Web Billing**, **Web-to-App Funnels**, **Build vs. buy**. The body never mentions them.
- **Undersold:** Charts (shown as "15+ metrics," missing LTV prediction / paywall-performance charts / REST-API access) and Experiments (shown as "A/B paywall testing," missing multivariate + predicted-winner-at-significance).
- **Wrong altitude / dilution:** a dev-onboarding "Connect the SDK" section and a 5-persona router that gives Marketing/Data/Support/Eng equal billing with Product on a *PM* page.
- **Thin proof:** one mojo.video testimonial + a logo strip; **no quantified outcomes** anywhere.
- **Keep (works):** benefit-led "you ship X, we handle Y" hero · dual CTA (Start free + Talk to sales) · logo band placement · interactive dashboard demo · scannable H2+body+CTA rhythm.
- **Net mandate for Track 5:** promote Paywalls/Web/Funnels/build-vs-buy into a **story-led, PM-owned, jobs-to-be-done arc** with **quantified proof** — replacing the feature grid and the persona router. (Full keep/cut/add table in Track 4.)

## I. Product depth & integrations
From [Track 2](02-product-context.md) — the footer-surfaced capabilities the live page lists but never explains. Promote them into the story.

- **Integrations ecosystem (the strongest net-new asset) — 40+ named tools** across Attribution/MMP & ads (AppsFlyer, Adjust, Branch, Singular, Kochava, Tenjin, Apple Search Ads, Meta Ads), Analytics/CDP (Amplitude, Mixpanel, Segment, mParticle, PostHog), Marketing/retention (Braze, OneSignal, Airship, Iterable, CleverTap, Customer.io, Intercom), Data warehouse (S3, GCS, BigQuery, Snowflake, Redshift), plus Slack, Stripe, and Webhooks. **This is the concrete proof behind the abstract "single source of truth / connects to your stack" claim** — RC normalizes events across platforms and pipes one revenue truth into the tools the team already uses. **HIGH** ([docs/integrations](https://www.revenuecat.com/docs/integrations/third-party-integrations)).
- **SDK breadth:** iOS (Swift/SwiftUI/Obj-C), Android (Kotlin/Java), React Native (Expo uses this SDK), Flutter, Unity, Cordova/Ionic/Capacitor, Web/JS, Kotlin Multiplatform, Mac Catalyst. **HIGH.**
- **Rico — the AI agent (public beta):** account-aware agent in **Slack** (`@Rico`) and the dashboard; answers MRR/churn/retention/ARPPU + "why did this metric move," and benchmarks you against the *State of Subscription Apps* dataset. PM value: self-serve monetization answers in the tool you live in. **HIGH** ([feature/ai-agent](https://www.revenuecat.com/feature/ai-agent)).
- **Customer Center:** drop-in in-app self-serve UI (cancel, restore, change plan/refund on iOS, contact support) that **auto-surfaces retention/win-back offers before a cancel completes** + configurable cancellation exit-surveys. PM value: deflect tickets, intercept churn at the moment of cancel, capture *why* users leave — no code/release. **HIGH** ([docs/tools/customer-center](https://www.revenuecat.com/docs/tools/customer-center)).
- **Targeting (deeper):** rules engine serving distinct Offerings/paywalls by custom attributes, country (storefront/geo), app/store, app version (semver), SDK version, platform; first-match-wins; experiment enrollment evaluated **before** targeting. PM value: match offer↔segment and graduate experiment winners into permanent rules in one move. **HIGH** ([docs/tools/targeting](https://www.revenuecat.com/docs/tools/targeting)).
- **Web Purchase Button / Links:** in-app button routing eligible buyers to a Web Billing (Stripe) checkout; tracked via webhooks, unlocks the same in-app entitlements via Redemption Links; positioned for Apple's post-Epic 2025 external-purchase rules; avoids the 15–30% store cut. **MEDIUM** (companion of Web Billing; mechanism partly inferred).
- **Daily payouts — ⚠ frame carefully:** a **revenue *advance*** — RC fronts ~80% of the prior day's revenue next-day (less a fee) to bridge the 30–60-day store payout lag. **NOT** a merchant-of-record change, **NOT** a change to store payout schedules; gradual rollout, initially US entities. Don't overclaim on the page. **MEDIUM** (CEO talk + webinar hub; no standalone docs page yet).
- **Reconciliation:** "Web purchase button" + "Daily payouts" are part of the brief's **Web Billing** family (companions, not new/renamed products); "Paywalls AI Editor" + "Figma export" corroborate the brief's Paywalls claims. **No contradictions with the brief.**

## J. Soft / do-not-lean-on
- ~~Buffer logo (gone from current site)~~ → **corrected: Buffer IS on the live `/for-product/` page** (screenshot-confirmed). Safe to use; not stale.
- **Stripe / Paddle** → **de-scoped from the competitive set** (web-only, partly RC complements). Competitive set = Adapty · Superwall · build-in-house. (Stripe/Paddle remain product facts in §0: Web Billing uses Stripe; Web Funnels can use Paddle.)
- In-house build-cost **dollar figure** — still no PRIMARY mobile-IAP-scoped source; use "months of eng + maintenance," not a hard number (Abbacus $200K–500K is the best non-vendor anchor but is whole-system, not IAP-only).
- **All RC scale numbers — confirmed vendor-only, no third party verifies them** (now established as a finding, not just a caveat). Lead with BCV's "~1/3 of new subscription apps" + marquee brands instead.
- Customer outcome %s except Floga (no disclosed baseline/date/methodology — direction trustworthy, exact number illustrative-of-real).
- Adapty's $3B / 16K-app benchmark sample (self-reported, unverifiable).
- Most demand-side benchmark stats (10.7%/2.1%, 80%/−33%, 55.4% Day-0) are from RC's *own* *State of Subscription Apps* report — VENDOR/PRIMARY; cite as "RevenueCat's 2026 report," never as a specific app's guaranteed result.
- ~~"Top-100 ship 3× more often"~~ → **removed: unverified in any primary source.**

---

## Recommended follow-up (optional polish)
The originally-flagged targets are now **resolved** (build cost corrected upward; third-party scale corroboration established as nonexistent; Stripe/Paddle de-scoped from the competitive set). Remaining nice-to-haves, none blocking Track 5: (1) a **browser-screenshot pass** of the live page (Chrome DevTools MCP) to capture the exact current logo set for the visual before/after; (2) a quantified outcome stat from a *named* enterprise customer beyond Floga/Pixelcut. **The sheet is review-ready for Track 5 synthesis.**

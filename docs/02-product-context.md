# Track 2 — Product Context (What Shipped)

**Focus (product only):** translate every capability into PM value. *Inputs, not a checklist* — the brief forbids a laundry list. Audience → [01](01-audience-research.md); competitive/pricing → [03](03-competitive-and-build-vs-buy.md); proof/stats → [07](07-proof-and-credibility.md); full brief canon → [fact-sheet §0](fact-sheet.md).

**Legend:** ✓ = `✅ PDF` (in the brief — 100% authoritative). ⚠ = site/inferred, not in PDF — keep with caution. All ✓ claims checked against the brief PDF (pp.2–4).

## What's new since the page was last updated
Each = sub-features · GA · verbatim PDF insight (the insight is the safest on-page claim).
- **Paywalls** ✓ — remote no-code config of the *entire* paywall, no code/app update. Visual drag-and-drop editor (templates or blank canvas), AI paywall generation, runtime custom variables (personalize copy via SDK), Figma export, full branding system (colors/fonts). **GA iOS/Android/RN/Flutter/web.** *Insight: "paywall iteration no longer requires a designer, engineering sprint, or App Store review cycle."*
- **Web-to-App Funnels** ✓ — no-code web→app onboarding funnels: multi-step screens, branching (URL params / survey answers / country), connected web checkout (**RevenueCat Billing or Paddle**), publish to hosted URL — no eng. Per-step analytics (conversion + drop-off) + UTM tying revenue to campaign. End-user flow: ad → personalized onboarding → web checkout → Redemption Link → app opens with sub active. *Insight: "capture, qualify, and convert users before they ever touch the App Store — improving attribution, reducing platform fees, enabling faster experimentation."*
- **Charts** ✓ — (1) **LTV Prediction & Cohort Explorer**: Prediction Explorer estimates future LTV/revenue; Cohort Explorer measures Revenue / Realized LTV / Retained Subs by cohort & period; trials now included in LTV predictions. (2) **4 real-time paywall-performance charts**: encounter rate, conversion rate, LTV by paywall, abandonment. (3) **Charts API**: programmatic access to all subscription analytics (revenue/churn/active subs/more) for dashboards/reports/AI pipelines. (4) **Apple Search Ads segmentation**: filter by ASA keyword/claim type. *Insight: "Charts are the analytical layer that connects paywall decisions, experiment results, and acquisition spend to actual business outcomes."*
- **Web Billing** ✓ — web purchases that work with mobile: hosted Web Paywall Links or Web SDK, Stripe, Apple Pay & Google Pay, multi-currency, intro pricing, self-serve customer-portal upgrades; auto-unlock in-app entitlements via Redemption Links. *Insight: bypasses app-store commissions (typically 15–30%), full pricing flexibility, pre-launch revenue — Floga: six figures in a single day before the app was live* (full proof → 07).
- **Experiments** ✓ — A/B tests on paywalls/pricing/packaging, now: **multivariate A/B/C/D** (up to 4 variants); **predicted 12-month LTV winners** (forward-looking signal *mid-experiment* once enough conversion data); **one-action winner rollout** (update offering / create targeting rule in one click); **draft mode**. *Insight: "predict long-term revenue impact and ship winners faster, with less manual work."*

### Brief-named capabilities outside the "What's New" body (PDF-authoritative, pp.4 pain table)
- **Automated Refund Handler** ✓ — brief's answer to *"platform policy volatility and refund abuse."* No mechanism detail in the brief; treat as a named capability.
- **Targeting rules engine** ✓ — brief's answer (with Web Funnels branching) to *"one-size-fits-all monetization"*; also inside Experiments' one-action rollout. Serves different offerings/paywalls per segment. (Deeper mechanics in [footer capabilities](#footer-surfaced-capabilities--ecosystem) below.)

## Still-relevant legacy use cases (carry old + new) ✓
Current page's 4 use cases; brief says they "are still relevant and important" and to merge old + new into one story:
1. Reduce eng time on maintenance & monetization changes ✓
2. Reduce multi-platform complexity ✓
3. Single "source of truth" of monetization data & reporting ✓
4. Improve conversion by A/B testing pricing/packaging/paywalls ✓

## Capability → PM-value table
The artifact Tracks 5/7 draw from. *Feature → benefit → job done.* Source: PDF / site / inferred. (Proof column = short claim; full verbatim insights above.)

| Capability | What it is | PM benefit | PM job (JTBD) | Proof / source |
|---|---|---|---|---|
| **Paywalls** | Remote config of entire paywall, no code/app update; drag-and-drop + AI gen. | Ship/restyle paywalls yourself → no eng sprint, no designer dep, no review wait. | "Iterate monetization UX as fast as the product, without a release." | GA iOS/Android/RN/Flutter/web (PDF) |
| **Experiments** | A/B/C/D on paywalls/pricing/packaging; predicted 12-mo LTV winner; 1-click rollout; draft mode. | See the *long-term-revenue* winner mid-flight → decide on LTV, not conversion; roll out in one click. | "Know which pricing/packaging grows revenue, ship the winner without manual work." | Predicted 12-mo LTV winners (PDF) |
| **Web Billing** | Web purchases (hosted links/Web SDK) unlocking in-app entitlements; Stripe, Apple/Google Pay, multi-currency. | Web revenue channel skipping 15–30% fees + full pricing freedom + pre-launch sales. | "Add a higher-margin channel and earn revenue before the app is live." | Bypasses 15–30%; Floga six figures/day pre-launch (PDF) |
| **Web-to-App Funnels** | No-code web onboarding → web checkout → Redemption Link → app opens with sub active. | Capture/convert on web before the store, with branching + per-step analytics. | "Turn ad spend into qualified, attributed subscribers before the App Store." | Per-step analytics + UTM (PDF) |
| **Charts (LTV Prediction + Cohort Explorer)** | Predict future LTV/revenue; measure Revenue/Realized LTV/Retained Subs by cohort & period (trials incl). | See where revenue is heading, not just where it's been → catch issues early. | "Forecast revenue and catch churn/LTV problems before the P&L does." | Trials now in LTV predictions (PDF) |
| **Charts (Paywall Perf + API + ASA)** | 4 real-time paywall charts; API for all subscription data; ASA-keyword segmentation. | One analytical layer ties paywall/experiment/spend decisions to outcomes; pipe data anywhere. | "Connect what I changed to the revenue it produced — in my own dashboards." | Charts API; analytical layer (PDF) |
| **Targeting rules engine** | Serve different offerings/paywalls per segment; powers experiment rollouts. | Past one-size-fits-all → tailor pricing/packaging by segment, no code. | "Match the right offer to the right user without a release or eng ticket." | PDF answer to "one-size-fits-all" |
| **Automated Refund Handler** | Automated refund / refund-abuse handling. | Insulate revenue from policy swings + refund abuse without manual ops. | "Protect revenue from store-policy volatility without building tooling." | PDF answer to "policy volatility & refund abuse" |
| **Cross-platform single source of truth** *(carried)* | One system unifying subscription data across iOS/Android/web. | Stop reconciling per-store data → one trusted reporting layer. | "Trust one number for revenue across every platform." | Legacy use case, "still relevant" (PDF + site) |
| **Reduce eng time on monetization** *(carried)* | Offload billing infra / monetization maintenance. | PMs (who don't write billing code) stop being blocked on eng. | "Move on monetization without spending eng roadmap on plumbing." | Legacy use case (PDF + site) |

## Footer-surfaced capabilities + ecosystem
Real current capabilities the live page lists in the footer but never explains (none contradicts the brief). Full detail → [fact-sheet §I](fact-sheet.md).
- **Integrations ecosystem (biggest net-new asset): 40+ named tools** — MMP/attribution (AppsFlyer, Adjust, Branch, Singular, Kochava, Tenjin, ASA, Meta), analytics/CDP (Amplitude, Mixpanel, Segment, mParticle, PostHog), marketing (Braze, OneSignal, Airship, Iterable, CleverTap, Customer.io, Intercom), warehouse (S3, GCS, BigQuery, Snowflake, Redshift), + Slack, Stripe, Webhooks. **Concrete proof behind the abstract "single source of truth / connects to your stack."** SDKs: iOS, Android, RN, Flutter, Unity, Cordova/Ionic/Capacitor, Web/JS, KMP, Mac Catalyst. (site, HIGH)
- **Rico (AI agent, beta)** — account-aware agent in Slack + dashboard; answers MRR/churn/retention/ARPPU, benchmarks vs *State of Subscription Apps* dataset. (site, HIGH)
- **Customer Center** — drop-in in-app self-serve (cancel/restore/change plan/refund) that auto-surfaces retention offers pre-cancel + exit surveys. (site, HIGH)
- **Targeting (deeper)** — rules by custom attributes, country, app/store, app version (semver), SDK version, platform; first-match-wins; experiments evaluated before targeting. (site, HIGH)
- **Web Purchase Button/Links** — in-app route to a Web Billing (Stripe) checkout; unlocks same entitlements via Redemption Links; avoids 15–30% cut. (site/inferred, MEDIUM)
- **Daily payouts** ⚠ — revenue *advance* (~80% of prior-day revenue next-day, less a fee) bridging the 30–60-day store lag. NOT merchant-of-record, NOT a store-schedule change; US rollout. Frame carefully. (CEO talk/webinar, MEDIUM)

**Output:** the capability→value table is the menu Track 5 picks the story from — **do not** put all rows on the page. Verify any claim against the brief PDF before it ships.

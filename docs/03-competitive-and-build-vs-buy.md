# Track 3 — Competitive Landscape & Build-vs-Buy

**Focus (competitive/pricing/build-vs-buy only):** how the page differentiates instead of describing. Two fronts; the second (build-vs-buy) is the real competitor and the one most submissions miss. Audience → [01](01-audience-research.md); product facts → [02](02-product-context.md) (not re-researched here).

**Notes.** *Sourcing:* initial draft via WebSearch+WebFetch; thin spots re-run with Perplexity MCP (corrections folded in below + in [Evidence quality](#evidence-quality--corrections-for-the-human-reviewer)). *Source tags:* PRIMARY (the org) / SECONDARY (aggregator) / PRESS / VENDOR (RC marketing, motivated) · confidence HIGH/MEDIUM/LOW; `(inferred)` = reasoned. *Brief canon (`✅ PDF`):* brief names **no competitors** — entire track is supporting research; the only relevant brief fact is commissions "typically 15-30%." *Positioning:* do **NOT** name competitors on the page; Front 1 sharpens our wedges, not comparison-shopping. If anything conflicts with the brief, brief wins.

---

## Front 1 — Named competitors

### Pricing reference (all % of revenue → directly comparable)
| Product | Free tier | Fee above free | Charges on | Source / confidence |
|---|---|---|---|---|
| **RevenueCat** | ≤ **$2,500** MTR/mo | **1%** of monthly tracked revenue | *All* tracked subscription revenue | revenuecat.com/pricing · PRIMARY · HIGH |
| **Adapty** | ≤ **$5,000** MRR/mo (rolling 30-day) | **1%** | All tracked revenue (subs, renewals, one-time), pre-store-cut | adapty.io/pricing · PRIMARY · HIGH |
| **Superwall** | ≤ **$10,000** MAR/mo | **1%** of MAR (+ optional $49/$199 plan fees) | **Only revenue attributed to Superwall paywalls** (MAR = Monthly *Attributed* Revenue), not total app revenue | superwall.com/pricing · PRIMARY · HIGH |
| **Build in-house** (StoreKit / Google Play Billing) | n/a (native) | $0 to any SDK vendor; **15–30%** store commission applies regardless | n/a | Apple Developer · PRIMARY · HIGH |

> % nuance: Superwall's $10K ceiling looks most generous **but** it bills only on paywall-attributed revenue and ships **no billing/entitlement backend** — a paywall layer, not a platform. Adapty & RC bill on *all* tracked revenue because they *are* the entitlement source of truth. Not apples-to-apples — matters for build-vs-buy. RC has the **lowest** free-tier entry of the three.

### Adapty
- **Known for:** closest direct competitor — subscription SDK + no-code paywall builder + A/B + analytics, aggressive benchmark-content engine (their report: **$3B across 16,000+ apps**, 2026 — adapty.io/state-of-in-app-subscriptions · VENDOR · MEDIUM, self-reported sample).
- **Pricing:** free under $5K MRR, then 1%.
- **RC stronger:** scale/ecosystem maturity (RC self-reports $14B+/yr, 50,000+ apps — VENDOR · MEDIUM); RC's forward-looking analytics (predicted 12-mo LTV winners, LTV Prediction — [02](02-product-context.md)) is a sharper PM-facing story than Adapty's benchmark/reporting; broader Web Funnels + Web Billing.
- **Adapty competitive/cheaper:** higher free ceiling ($5K vs $2.5K) → early-stage app pays RC first; core parity (SDK+paywalls+A/B+analytics) close; markets itself as the RC alternative. **Honest read: for a small app on price alone, Adapty is cheaper longer.**
- **Wedge:** out-position on completeness + intelligence (predicted LTV, funnels, web billing as one system), not "we also have paywalls."

### Superwall
- **Known for:** best-in-class paywall A/B + remote paywall design; loved by growth teams iterating aggressively. github.com/superwall/Superwall-iOS · PRIMARY · HIGH.
- **Pricing:** free under $10K MAR, then 1% of paywall-attributed revenue; optional $49/$199.
- **Moved upmarket (key finding):** PM page now claims *"the central engine for subscription product growth"* and *"the single source of truth for your subscription product"* — direct collision with RC. **But** its own docs route billing/product definition *"through RevenueCat,"* its web checkout is a Stripe deep-link unlocking entitlements *in your app*, and it bills only on attributed revenue → a paywall **surface**, not the billing source of truth. Teams run Superwall *on top of* RC. (superwall.com + /docs · PRIMARY · HIGH)
- **RC stronger:** Superwall is a paywall/experiment layer, not a billing/entitlement backend — you still need receipt validation, cross-platform entitlements, web billing, source of truth. RC is the full stack.
- **Superwall stronger:** pure paywall-iteration UX + experiment velocity (their entire focus, widely regarded excellent); highest free ceiling. If a PM only wants to A/B paywalls and billing is solved, Superwall is a strong cheap choice.
- **Wedge:** *"Paywalls are the surface; entitlements are the source of truth"* — a standalone paywall tool still leaves you owning billing, entitlements, the source of truth.

### Build in-house (StoreKit / Google Play Billing) — *the real competitor*
The named competitor that matters most for this audience; full cost analysis = **[Front 2](#front-2--build-vs-buy-the-real-competitor)**.
- **Known for:** the "free" first-party path (Apple StoreKit 2, Google Play Billing Library); no SDK vendor fee — what eng proposes when a PM asks "can't we just build this?"
- **"Pricing":** no vendor cost, but **15–30%** store commission applies either way. *Precise breakdown:* Apple standard **30%**, but **Small Business Program = 15%** (≤$1M net proceeds/yr), and auto-renewable subs drop to **15% after a subscriber's first year**; Google Play **15%** on the first $1M/yr per developer and 30% above for one-time/IAP, but **subscriptions 15% from day one**. (developer.apple.com/app-store/small-business-program · PRIMARY · HIGH)
- **Reality:** technically free, but shifts the entire validation/entitlement/cross-platform/edge-case/maintenance burden onto eng; every paywall/pricing change becomes an app release + store-review cycle.
- **Wedge:** "free" native APIs are the most expensive option once you price in eng time, edge cases, and release-cycle drag (Front 2).

---

## Front 2 — Build-vs-buy (the real competitor)

**Most important section.** For a monetization/growth PM who owns revenue but doesn't write billing code, the true alternative is almost always *"engineering will just build it in-house."* The page must defeat that implicitly, never saying "don't build it."

### A. The hidden cost is *correctness*, not the happy path (first-hand eng evidence)
Best non-vendor evidence: **Pratilipi**'s write-up on building a "correct" StoreKit 2 backend in-house — the hard part is edge cases, not the initial integration:
- **`originalTransactionId` is "stable — until it isn't":** Apple can emit a *new* one for the same user after account/country/billing changes → **multiple temporarily-active IDs**, undocumented timing; naive backends double-grant or mis-resolve.
- **The only reliable user id (`appAccountToken`) can be missing/unreliable** — older clients omit it, no guarantee of presence → defensive "if missing, don't grant" logic.
- **Active/inactive modeling is wrong:** grace periods, retry windows, revocations each have distinct access implications; naive model revoked too early / extended too long / showed UI mismatching billing reality.
- **Billing truth, access state, history evolve differently** → must be separated (a single combined service broke).
- Source: Ayush Singh / Team Pratilipi, *"Building a Correct Backend for App Store StoreKit 2"* (medium.com/team-pratilipi/...eba023158961) · PRESS/PRIMARY first-hand · **HIGH** these edge cases exist (MEDIUM generality — one team).

### B. State complexity Apple itself documents (some untestable)
- A renewal failure → **grace period** (configurable **3/16/28 days**): Apple considers the sub **active**, billing is **failing**, user **retains access** — three truths to reconcile. Then Apple retries billing **up to 60 days**.
- **Grace periods don't exist in Apple's sandbox** → can't test grace handling before production.
- Correctness under retries needs **idempotency keyed per event type** (purchases/re-subscriptions by `originalTransactionId`, renewals by `transactionId`, refunds by `transactionId` w/ fallback).
- Sources: Apple Developer — *Testing failing subscription renewals* (PRIMARY · HIGH); Adapty grace-period tutorials (SECONDARY, competitor-authored · MEDIUM).

### C. The multiplier: build it *twice* (iOS + Android), then web
All of A/B — receipt/transaction validation, server-side state machine, grace/retry, refund logic, entitlement sync — must be rebuilt for **Google Play Billing** (different API, lifecycle, server notifications), then again for web. This duplication is exactly what RC's "single source of truth across iOS/Android/web" attacks (legacy use cases #2/#3, [02](02-product-context.md)). `(inferred — structural fact that Apple/Google billing are separate stacks; strongly supported, not one citation.)`

### D. Quantified cost anchors (frame, don't price)
- The indie figure ($12–24K / 2–4 weeks at $150/hr, buildmvpfast · SECONDARY · LOW–MEDIUM) is **too low**. Best non-vendor anchor: **Abbacus Technologies** — intermediate subscription-billing system **$200K–$500K over 6–9 months + 15–25%/yr maintenance**; the mobile-IAP "core engine" slice (~30–50%) ≈ **$60K–$250K / 2–9 engineer-months**. **Page guidance:** frame in-house as *"months of engineering + a permanent maintenance burden,"* **not** a hard dollar number (no PRIMARY source nails exact mobile-IAP scope). The indie source's own caveat — math flips >$25K/mo for simple iOS-only apps — is the honest counterpoint.
- **Vendor anchor (motivated):** RC's build-vs-buy page cites a dev who replaced **~37,000 lines** of in-house subscription code with **~1,000 lines** of RC, "eliminating their role as a part-time subscription engineer." revenuecat.com/build-vs-buy · VENDOR · LOW — narrative color, not proof.

### E. The PM-specific cost: release-cycle drag (what PMs feel most)
Maintenance/correctness is the *eng* cost; the **PM** feels **velocity**: monetization in app code → every paywall/price/packaging change = eng ticket + app build + App Store review. RC's core promise (PDF-verified, [02](02-product-context.md)): *"paywall iteration no longer requires a designer, engineering sprint, or App Store review cycle."* Build-in-house permanently couples monetization experiments to the release train. **Most defensible, most differentiated build-vs-buy argument for this audience** — grounded in a brief-verified product claim, not a vendor stat.

**Synthesis (implicit, never named):** "Free" in-house = a permanent, growing tax of edge-case correctness across 2+ billing stacks, paid in eng time and roadmap velocity — while every change waits on a release. Buying makes monetization something the PM moves on this week, not next quarter.

---

## Differentiation angles to test
Three wedges (feed Track 5; full version → [fact-sheet §F](fact-sheet.md)), each tied to evidence above + brief-verified product facts ([02](02-product-context.md)):
1. **Velocity / independence — "ship monetization without shipping code."** Backed by release-cycle drag (E) + brief-verified Paywalls claim. Strongest: directly defeats build-in-house, hits the PM's actual pain, grounded in a verified claim. **Lead with this.**
2. **Completeness — "a platform, not a point tool."** Backed by Front 1 — Superwall is paywalls-only, build-in-house is backend-only; RC unifies entitlements + paywalls + experiments + web billing + funnels + analytics as one source of truth. Defeats "stitch point tools" *and* "build the connective tissue ourselves." Pairs with the cross-platform single-source-of-truth carry-over.
3. **Forward-looking intelligence — "decide on predicted LTV, not lagging conversion."** Backed by brief-verified Experiments (predicted 12-mo LTV winners mid-flight) + Charts LTV Prediction. Clearest *substance* win over Adapty/Superwall; reframes category from "test conversion" → "predict revenue." Differentiating third beat, not the headline.

> **Won't do on the page:** name competitors, or compete on free-tier ceiling / price (we'd lose to Adapty $5K, Superwall $10K). Compete on velocity, completeness, intelligence.

---

## Competitive map (adjacencies & status)
Full synthesis → [fact-sheet §D](fact-sheet.md). (Superwall's upmarket move folded into its Front-1 entry above.)
- **Status:** Qonversion **active** (did not shut down). Glassfy **acquired by RC (2023)** + sunset — consolidation proof point. Nami ML / Purchasely active (smaller, design/ML-led). Lemon Squeezy acquired by Stripe (2024, PRESS).
- **Complements, not rivals:** Amplitude/Mixpanel + MMPs (AppsFlyer/Adjust/Branch) **consume** RC's server-side renewal/refund events to keep LTV/ROAS accurate (critical under SKAdNetwork) — reframe as "RC feeds your stack," not threats.
- **Native price experiments** only A/B **store-listing assets** (icons/screenshots), not in-app paywall UI — the gap RC's remote paywalls/experiments fill.
- **Separating axes:** point-tool vs platform · mobile-IAP vs web vs cross-surface · lagging conversion vs forward-looking LTV · paywall-surface vs source-of-truth. **RC = the source-of-truth substrate that also ships the surface.**

## Evidence quality & corrections (for the human reviewer)
Confidence tags; corrections resolved against primary sources once Perplexity MCP came online. Handle anything below HIGH with care before it reaches the page.
- **Confirmed (HIGH):** competitor pricing (RC $2.5K MTR / Adapty $5K / Superwall $10K MAR, then 1%); Superwall MAR = Monthly *Attributed* Revenue; RC lowest free-tier entry.
- **In-house build cost — framed not priced** (see D): indie $12–24K too low; Abbacus $200–500K / mobile slice $60–250K; present as months + maintenance.
- **Soft claims (handle with care):** RC scale ($14B+/yr, 50,000+/106K apps, ~3B req/day, 96.3% support sat) + the 37k→1k anecdote = **VENDOR-authored**, **no third party independently verifies** them (SaaStr/Subscription Insider/BCV/The SaaS News all *attribute* to RC) → present as "RevenueCat-reported"; lean on BCV's third-party-acknowledged *"powers over one-third of all new subscription apps worldwide"* + marquee brands (ChatGPT, Notion, Perplexity). Adapty $3B/16k sample self-reported (MEDIUM). Pratilipi edge cases first-hand (HIGH they exist, don't imply universal). Build-twice multiplier `(inferred)`.

**Output:** the 3 wedges (velocity / completeness / forward-looking intelligence) + a build-vs-buy framing grounded in real eng edge-case evidence (Pratilipi + Apple docs) and the PM-felt release-cycle-drag argument.

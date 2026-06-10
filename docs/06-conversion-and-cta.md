# Track 6 — Conversion & CTA Strategy

**Job:** It's a landing page — its job is to *lead the reader to action*. This is the funnel logic of the page (distinct from visual design): the one action we want, the CTA ladder that serves both enterprise and SMB PMs, where proof de-risks each decision moment, and where every objection from [Track 1's Question-Exhaustion Map](01-audience-research.md#question-exhaustion-map-the-page-must-answer-every-one) gets answered *next to the CTA it would otherwise stall*.

> ⚠ **Pillar names provisional — reconcile with Track 5 once its messaging brief lands.** Track 5 (positioning/pillars) is still a stub. Below I use the three brief-canon differentiation wedges (`CLAUDE.md` → *velocity/independence · completeness/source-of-truth · forward-looking intelligence*) as working **value-section** scaffolding. Proof and CTA placement are framed around generic "value sections V1–V4" so they survive whatever final pillar names Track 5 commits.

> **Ground-truth note (verified live 2026-06-06 via WebFetch):** the real CTAs and signup model are confirmed, not invented —
> - `revenuecat.com` hero + footer: **"Start for free"** (primary) / **"Talk to sales"** (secondary); nav has **"Log In"** / **"Sign Up"**.
> - `revenuecat.com/for-product/` hero: **"Request a demo"** / **"Explore Product Demo"**; closing section: **"Start for free"** / **"Talk to sales"**.
> - Signup model: self-serve, **free until $2,500 in monthly tracked revenue** ("Only pay when you earn… usage-based pricing starts after you reach $2,500 in monthly tracked revenue"); 1% of MTR thereafter. Enterprise/demo path runs in parallel via "Talk to sales" / "Request a demo."
> All CTA copy proposed below is built from this verified vocabulary. Nothing here invents a flow, price, or product that doesn't exist.

---

## Primary conversion goal

**The one action: self-serve account creation — "Start for free."**

**Assumption (logged):** the dominant primary CTA across the page is **"Start for free"** (self-serve signup), with **"Talk to sales"** as a co-equal-prominence secondary for the enterprise motion. This is an assumption about *priority*, justified below; it is **not** an assumption about *availability* — both paths verifiably exist on RC's live site today.

**Why self-serve is primary (not "request a demo"):**
- **Audience intent.** Track 1's reader is a Monetization/Growth PM who owns the revenue lever but is **blocked by release latency**, and who is often **scoping build-vs-buy**. Their highest-intent next step after a velocity promise is to *see it work themselves*, not to schedule a sales call a week out. The current `/for-product/` page leads its hero with "Request a demo" — a higher-friction, sales-gated ask that suits enterprise but **stalls the SMB/indie PM and the self-directed evaluator**. Promoting "Start for free" corrects that.
- **The product's own model rewards it.** RC is free to $2,500 MTR — there is *no commercial reason* to gate the SMB PM behind sales. "Start for free" + "no charge until you're earning" is a frictionless, honest, conversion-maximizing primary.
- **It defeats build-vs-buy fastest.** The cheapest rebuttal to "we'll build it in-house" is *"you could be live this week, for free"* — only the self-serve path delivers that proof.

**Serving both audiences (the page is explicitly dual-motion):**
- **SMB / indie PM →** primary path = **"Start for free"** (speed, free tier, no eng team needed). This is the dominant button.
- **Enterprise PM →** parallel path = **"Talk to sales"** (reliability at scale, security/governance, dedicated support). Co-located with the primary at hero and close so the enterprise reader never has to hunt. A lighter **"Explore the product demo"** (interactive, no form) serves the not-ready-to-talk enterprise evaluator who wants to look before booking.

**Success signal (hand to Track 9 / Track 0):** primary = **free-account signups** (clicks on "Start for free" → completed signup). Secondary = **qualified "Talk to sales" requests** (enterprise pipeline). Page-health proxies: scroll-depth past the build-vs-buy section, and interactive-demo engagement. One number to optimize: **self-serve signup conversion rate**, segmented by SMB vs. enterprise referral source.

---

## CTA hierarchy

A **two-tier ladder repeated at every decision moment**, plus a third no-commitment "look" option in places where the reader wants evidence before any ask.

| Tier | Button copy | Commitment | Audience it serves | Where it appears |
|---|---|---|---|---|
| **Primary (dominant)** | **Start for free** | Low (self-serve, free to $2.5K MTR) | SMB/indie + self-directed evaluator | Hero, every value-section footer, closing CTA, sticky nav |
| **Secondary** | **Talk to sales** | Medium (sales conversation) | Enterprise | Hero, closing CTA, sticky nav |
| **Tertiary ("look," no form)** | **Explore the product demo** | None (interactive, no signup) | Not-ready evaluators (both) | Hero (text link under buttons), after the Paywalls/velocity value section |

**Copy rules applied (Track 1 vocabulary — action + value, never "Learn more"):**
- Buttons carry **action + value**. The dominant button stays **"Start for free"** verbatim (verified live copy; high-converting and on-brand) — its *value* ("free until you're earning") is carried by the **microcopy directly beneath it**, not crammed into the label.
- Value-section CTAs may localize the verb to the section's job while keeping "free" honest, e.g. after the Paywalls section: **"Ship your first paywall free"**; after Experiments: **"Run your first experiment free."** These are still self-serve signups — same destination, contextualized promise.
- **Banned:** "Learn more," "Get started" (vague), "Submit," "Click here." Replace any "Learn more" with a value-bearing verb or the tertiary **"Explore the product demo."**

### Existing page CTAs (baseline — verified live, revenuecat.com/for-product/, 2026-06-06)

What the current page actually ships today, top to bottom, so our changes are deltas against a real baseline (not invented):

| # | Live CTA (exact text) | Location on current page |
|---|---|---|
| — | **Sign Up** / **Log In** | Top nav (persistent) |
| 1 | **Request a demo** | Hero — *primary* |
| 2 | **Explore Product Demo** | Hero — *secondary* |
| 3 | **Read case study** | Customer-proof block |
| 4 | **Try the demo** | "Explore the Dashboard" section |
| 5 | **Get started** | "Proactively improve your product" (retention) section |
| 6–10 | **Learn more** ×5 | Marketing · Data · Product · Support · Engineering team-role sections |
| 11 | **Start for free** | Final CTA ("Ready to grow?") — *primary* |
| 12 | **Talk to sales** | Final CTA — *secondary* |

**What we keep / change vs. this baseline:**
- **Keep** the dual self-serve + sales pattern (it already serves SMB and enterprise) and the interactive **"Explore Product Demo" / "Try the demo"** no-form option — strong for a technical PM buyer.
- **Change the hero hierarchy:** the live hero leads with **"Request a demo"** (sales-first). We promote **"Start for free"** to the dominant hero action and demote sales to the co-located secondary — matching the *bottom*-of-page pairing the page already uses at its final CTA, but moving it above the fold. (Logged as the priority assumption in [Track 0](00-process-and-assumptions.md).)
- **Cut the five "Learn more"** team-role CTAs — they're the exact vague pattern the copy rules ban; replace with value-bearing verbs or the tertiary demo link.
- **Keep "Start for free" + "Talk to sales" verbatim** at the close (the live closing copy is already on-brand and converting).

**Placement logic (one CTA pairing per decision moment):**
1. **Hero** — Primary + Secondary side by side; tertiary demo link beneath; price-honest microcopy under the primary.
2. **After each value section (V1–V4)** — a single contextual primary ("Ship your first paywall free", etc.). Don't double up enterprise CTAs mid-scroll; keep momentum on self-serve, let proof do the enterprise reassurance.
3. **Build-vs-buy section** — primary CTA appears **immediately after the in-house-cost reframe** (this is the closest pairing to the primary CTA — see objection handling). Copy: **"Start for free"** with microcopy *"Live this week, not next quarter."*
4. **Closing CTA** — full pairing again: **"Start for free"** + **"Talk to sales"**, mirroring the verified live close, under a thesis-restating headline.
5. **Sticky/nav** — persistent **"Start for free"** (+ "Talk to sales" on desktop) so the decision is always one click away regardless of scroll position.

---

## Proof placement

**Principle:** proof sits **immediately after the claim it backs and immediately before/beside the CTA that claim motivates** — so the riskiest moment (the click) is the best-evidenced moment. Pull only from Track 7's verified library; **no Buffer logo** (Track 7: unverifiable on current site), and **scale numbers framed as RevenueCat-reported.**

| Page location | Proof asset (from Track 7) | What it de-risks |
|---|---|---|
| **Hero proof strip** (under CTAs) | **"106,000 apps · $14B+ processed annually"** (RC-reported) + marquee logos **OpenAI/ChatGPT, Notion** | "Is this real / who else trusts it?" — instant scale + peer trust at the first decision moment. Use the homepage pair (106K/$14B), **not** the report pair (115K/$16B), per Track 7's mismatch note. |
| **V1 — Velocity / "ship without shipping code"** (Paywalls) | **Hard-paywall benchmark: 10.7% vs 2.1% D35 trial-to-paid (~5×)**; reinforce with the **"3× faster than building ourselves" (Floga)** line | Proves the paywall is the lever *and* that iterating it fast pays — directly before the "Ship your first paywall free" CTA. |
| **V2 — Completeness / source-of-truth** (entitlements, cross-platform, web) | **Floga: six figures in a single day, pre-launch, commission-free** (brief's own proof — use "six figures," not "$120K", per brief canon) + platform-coverage trust row (iOS/Android/RN/Flutter/web GA; Stripe/Apple Pay/Google Pay; SOC 2 · GDPR) | De-risks "is the whole funnel really here / is web real?" and the enterprise compliance question, beside the completeness CTA. |
| **V3 — Forward-looking intelligence** (Experiments + predicted LTV) | **Pixelcut: +16% paying customers from one A/B test** ("this test alone paid for all of RevenueCat's costs") | Turns "will experiments actually move revenue?" into a self-funding argument right before "Run your first experiment free." |
| **Build-vs-buy section** | **Floga "3× the time to build ourselves"** + **3B+ API requests daily** (battle-tested infra you don't have to build) + the edge-case correctness checklist (Track 3: grace periods, refund handling, dual iOS/Android stacks) | This is the highest-stakes objection; it gets the heaviest proof, sitting between the reframe and the primary CTA. |
| **Closing CTA** | Logo wall (OpenAI/ChatGPT, Notion, VSCO, ElevenLabs, Pixelcut, Runna, Ladder) + one outcome stat (**ElevenLabs $1M ARR in 16 days**, framed RC-reported) | Final peer-trust + outcome reassurance at the last decision moment. |

**Honesty flags carried from Track 7 (must hold on the page):** all RC scale numbers and customer outcomes are **vendor-reported** — present as RevenueCat's own figures, not audited; benchmark figures are **category** benchmarks ("across the category…"), never a promise of a specific app's result; **do not display Buffer**; never mix the 106K/$14B and 115K/$16B pairs.

---

## Friction & objection handling

Walking **every bucket** of Track 1's Question-Exhaustion Map. For each: the answer, and **where it sits relative to which CTA.** The build-vs-buy bucket gets the closest pairing to the primary CTA.

### Immediate (arises from the hero thesis) — answered *in or right below the hero / V1*
- *"Can I really change paywalls without shipping an app update?"* → **Yes — remote, no-code paywall config; no App Store review cycle.** Answered as the V1 sub-headline, directly above the V1 "Ship your first paywall free" CTA.
- *"Which platforms — iOS, Android, web?"* → **GA across iOS / Android / RN / Flutter / web.** Platform-coverage row in the hero proof strip and again in V2, so it's settled before any CTA.
- *"Do I need engineering at all?"* → **No-code editor + AI generation; engineering does one SDK integration once.** Microcopy beside the V1 CTA so the "but I'll need eng anyway" doubt doesn't stall the click.

### Decision-stage (close to acting) — answered *beside the primary CTA*
- *"How fast is it live — days or a quarter?"* → **Live this week** (microcopy under the build-vs-buy and closing primary CTAs) for SMB; **reliability-at-scale** proof (3B+ requests/day, marquee logos) for enterprise beside "Talk to sales."
- *"What does it cost / is there a free tier?"* → **Free until $2,500 in monthly tracked revenue; 1% after — you only pay when you earn.** This is **price-honest microcopy printed directly under every "Start for free" button.** Pre-empting the cost question at the CTA is the single most important friction-reducer for the SMB PM.
- *"How hard is integration/migration?"* → **One SDK integration, once; your team never rebuilds it per change.** Stated in V2 (completeness) and the build-vs-buy section, near their CTAs.

### Objection (doubts that stall) — *this bucket IS build-vs-buy; placed closest to the primary CTA*
- *"Why not just have engineering build paywalls/billing/experiments in-house?"* → **Concede then reframe** (per CLAUDE.md): acknowledge it's buildable, then surface the hidden cost — **edge-case correctness** (Apple grace periods you can't even test in sandbox, shifting `originalTransactionId`, refund handling), **built twice** (separate iOS + Android billing stacks, then web), and the PM-felt cost: **every monetization change permanently coupled to the release train.** Reframe: *"buying turns monetization into something you ship this week, not next quarter."* → This sits in its **own dedicated build-vs-buy section with the primary CTA immediately after the reframe** — the tightest objection→CTA pairing on the page.
- *"Is the cross-platform revenue data actually trustworthy?"* → **Single source of truth for entitlements across iOS/Android/web.** Answered in V2, beside its CTA.
- *"Will this break when Apple/Google change policy?"* → **Automated refund handling + platform insulation; we absorb the policy churn.** In the build-vs-buy section (it's part of the hidden-cost reframe) and V2.
- *"Is the A/B 'winner' real or short-term noise?"* → **Predicted 12-month LTV winners — decide on forecasted revenue, not lagging conversion.** Answered in V3 directly above "Run your first experiment free."

### Comparison (would trigger a new search) — answered *without naming competitors*
- *"How is this better than [other tools] / rolling our own?"* → **Completeness (the full funnel in one source of truth) + forward-looking LTV.** Handled implicitly by the V2 (completeness) and V3 (intelligence) value sections and the build-vs-buy reframe — **no competitor named** (CLAUDE.md rule). The wedges *are* the comparison answer; placement is the value-section CTAs, so a comparison-shopping reader gets the differentiation before leaving to search.

### Edge-case (niche but bounce-worthy) — answered *in V2 (web/completeness), near its CTA*
- *"Can I sell on web to dodge the 15–30% app-store cut?"* → **Web Billing + Web-to-App Funnels** (Stripe/Apple Pay/Google Pay; auto-unlock in-app via Redemption Links). V2.
- *"Can I earn revenue before the app launches?"* → **Yes — pre-launch web revenue (Floga: six figures in a day, pre-launch).** V2, as the proof beside the completeness CTA.
- *"Can I pull my subscription data into our own dashboards?"* → **Charts API (programmatic access).** V3 (intelligence), as a bonus line near its CTA.

> **The rule that matters:** the build-vs-buy objection is the real competitor for this audience. Its answer is the **only** objection given its own section *and* the closest physical pairing to a primary "Start for free" CTA — so the PM who is privately scoping "we'll build it ourselves" hits the reframe and the free-signup button in the same breath.

---

## Hero spec

**What it must communicate in 5 seconds:** *who it's for* (product managers who own monetization), *the thesis* (ship monetization changes without waiting on engineering or the release train), *the action* ("Start for free," with "Talk to sales" alongside).

**Structure (top to bottom):**
1. **Eyebrow:** `For product teams` (keep the live page's audience signal — it works).
2. **Headline (H1)** — lead with the velocity/independence wedge (the strongest, build-in-house-defeating one). Candidates:
   - **"Ship monetization without shipping code."** ← *recommended:* sharpest, most differentiated, directly names the release-latency pain.
   - "Own your revenue lever — without waiting on the release train."
   - "Change your paywall today. No app update. No eng sprint."
   - *(Keep-and-sharpen option, honoring Track 4's "preserve the hero construction":)* "You ship what matters. We handle monetization." — but **broaden "monetization"** to signal paywalls/experiments/web, or it stays generic (Track 4's exact critique).
3. **Subhead** — translate thesis → JTBD + completeness, in PM language: *"Launch and test paywalls, pricing, and web checkout on your own cadence — across iOS, Android, and web — from one source of truth. No app update, no App Store review, no engineering sprint."*
4. **Primary CTA:** **Start for free** · **Secondary CTA:** **Talk to sales** (side by side; primary visually dominant).
   - **Price-honest microcopy under the primary:** *"Free until you reach $2,500 in monthly tracked revenue."*
   - **Tertiary link beneath:** *Explore the product demo →* (interactive, no form — for the not-ready evaluator).
5. **Hero proof strip** (immediately under CTAs): **"106,000 apps · $14B+ processed annually"** (RC-reported) + marquee logos (**OpenAI/ChatGPT, Notion**) + a quiet platform row (**iOS · Android · React Native · Flutter · Web**). This de-risks the first decision moment and pre-answers the "which platforms?" immediate question before the reader scrolls.

**5-second test:** a Monetization PM landing from search sees *for product teams* → *ship monetization without shipping code* → *free to start / talk to sales* → *106K apps, OpenAI & Notion, all platforms*. Who it's for, the promise, the action, and the proof — without scrolling.

---

## Output

A conversion map handed to Track 9: **primary goal** = self-serve **"Start for free"** signups (enterprise served in parallel by **"Talk to sales"**); a **two-tier-plus-demo CTA ladder** placed at hero, every value section, the build-vs-buy section, the close, and a sticky nav, with action+value copy (never "Learn more"); **proof placed at each decision moment** (hero scale strip → V1 hard-paywall benchmark → V2 Floga/platform-coverage → V3 Pixelcut → build-vs-buy heavy proof → closing logo wall), drawing only on Track 7's verified library; **every Question-Exhaustion-Map bucket answered next to the CTA it would stall**, with build-vs-buy given its own section and the tightest pairing to the primary CTA; and a **hero spec** with recommended headline *"Ship monetization without shipping code."* All CTA copy and the free-tier model are **verified against the live site (2026-06-06)**. Reconcile provisional pillar/value-section names with Track 5 once its messaging brief lands; the placement logic is built to survive the renaming.

## Open questions / assumptions logged
*(append to Track 0)*
1. **ASSUMPTION:** primary CTA priority is self-serve **"Start for free"** over the live `/for-product/` hero's "Request a demo." Justified by audience intent (release-latency-blocked PM + build-vs-buy scoping) and the free-to-$2.5K-MTR model. Both paths exist live; this is a priority call, not an availability claim.
2. **VERIFIED (not assumption):** all CTA copy ("Start for free" / "Talk to sales" / "Request a demo" / "Explore Product Demo") and the **free-until-$2,500-MTR, then 1%** model — confirmed via WebFetch of `revenuecat.com` and `/for-product/` on 2026-06-06.
3. **PROVISIONAL:** value-section names V1–V4 map to the three brief-canon wedges (velocity · completeness · forward-looking intelligence) as scaffolding only — **reconcile with Track 5's committed pillars.** Placement logic is pillar-name-agnostic.
4. **OPEN:** exact post-click signup flow length/fields not audited (behind auth — WebFetch can't reach it). If signup is long, consider an interstitial value-recap; flag for Track 9 to verify the real flow.
5. **HONESTY CARRYOVERS (Track 7):** scale/outcome numbers are vendor-reported (frame as RC's own); use Floga's **"six figures"** (brief canon), not "$120K"; **no Buffer logo**; don't mix 106K/$14B with 115K/$16B; benchmarks are category-level, not per-app promises.
6. **OPEN:** sticky-nav CTA on mobile — confirm it doesn't crowd the viewport; Track 9/QA decision.

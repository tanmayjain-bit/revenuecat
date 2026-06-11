# RevenueCat PMM Take-Home

[![Live site](https://img.shields.io/badge/➜%20Live%20site-5B7FFF?style=for-the-badge&logoColor=white)](https://revenuecat-three.vercel.app/)

Submitted June 2026. This file is the process write-up.

---

## 1. AI tools used

- **Claude Code (Opus 4.8)** — orchestration, research synthesis, copy, positioning brief, and all code. Used via the CLI with a multi-track repo architecture; parallel subagent workflows fanned out research tasks concurrently.
- **Perplexity MCP** (`perplexity_ask`) — citation-backed sourcing for competitive facts, pricing, and market stats. Connected live as an MCP server inside Claude Code.
- **Chrome DevTools MCP** — measured exact design tokens (colors, typography, spacing) from the live `/for-product/` DOM via `getComputedStyle`; no guessing from screenshots.
- **WebSearch / WebFetch** — live page teardown, competitor site reads, RevenueCat homepage analysis.

---

## 2. Assumptions

| Assumption | Why reasonable | What changes if wrong |
|---|---|---|
| **Font substitution:** ship Hanken Grotesk (heads) + Inter (body) instead of RC's licensed Object Sans | Object Sans is a paid Pangram Pangram font; shipping it on a public deploy is a licensing violation. The brief says "brand-aware, not pixel-perfect." Hanken Grotesk is a near-identical free geometric grotesque. | Trivial token swap if a license is provided |
| **Velocity leads the narrative** among the 3 wedges | It's the claim that most directly defeats build-in-house, rests on the brief-verified Paywalls statement, and was the top unprompted signal in the primary ICP interview ("move wayyy faster"). | Pillars can re-order without touching section inventory |
| **Build-vs-buy is an objection, not a 4th pillar** | Elevating it to a pillar makes the page argue against a ghost instead of telling RC's own story. Brief says don't name competitors. | Promote to its own section if testing shows it needs more prominence |
| **Target audience narrowed to the Monetization/Growth PM** | The brief's JTBD describes exactly this person ("can't move fast," owns conversion/ARPU/LTV). A sharp persona beats a 5-persona router. Enterprise and SMB are served from common ground, not split paths. | Broaden hero copy; structure holds |
| **Primary CTA is "Start for free," not "Request a demo"** | The live `/for-product/` page leads with a sales-gated demo ask, which stalls the self-directed SMB PM. RC's model is free to $2,500 MTR, so there is no commercial reason to gate self-serve behind sales. | Swap CTA priority per conversion data |
| **Lead scale with BCV's "~1/3 of new subscription apps"** instead of RC's self-reported 106K apps / $14B tracked | Research found no third party verifies RC's self-reported scale figures. A sourced external stat is more credible to a skeptical PM. | Self-reported figures are ready as a swap |
| **Web Billing and Web Funnels kept secondary** | The primary ICP interview (iOS/Android-only PM at a high-growth app-first company, a current RC customer) expressed zero web interest. Brief still lists them as "What's New," so they earn a place, just not the lead. | Promote if the target audience tilts toward web-to-app funnels |
| **Desktop-only, no mobile responsiveness** | The brief's bar is a functional page judged as product marketing on a 4-6 hr budget. The reviewer will engage on desktop. Time is better spent on narrative quality and this write-up. | A static Tailwind page is straightforward to make responsive as an additive pass |

---

## 3. Process overview

The project ran as **parallel research tracks feeding a sequential synthesis**, with a hard build gate at Track 5 (positioning brief). No page code was written until the messaging brief existed.

**Phase 1 — Research (parallel, Tracks 1-4, 7-8)**
Three parallel Claude Code subagent workflows deepened each research area concurrently. Perplexity MCP provided citation-backed sourcing. A primary ICP interview with a current RC customer (Monetization PM at a high-growth iOS/Android app) provided first-party signal. Chrome DevTools MCP measured design tokens directly from the live DOM. All findings consolidated into [`docs/fact-sheet.md`](docs/fact-sheet.md) with per-claim source/confidence tagging and a brief-canon tier (§0) flagging verbatim PDF facts.

**Phase 2 — Synthesis (sequential, Tracks 5-6)**
Track 5 consumed the full fact-sheet and PM question chain to produce the messaging brief, 3 pillars, section arc, and deliberate cut-list. This resolved the build gate. Track 6 translated the positioning into a CTA hierarchy and objection-placement map. Full notes: [`docs/05-positioning-and-narrative.md`](docs/05-positioning-and-narrative.md) and [`docs/06-conversion-and-cta.md`](docs/06-conversion-and-cta.md).

**Phase 3 — Build (Track 9)**
Single static page under `site/` using Tailwind + measured brand tokens. No framework, no CMS, no i18n. Deployed to Vercel. Full process log (decisions, pivots, tool usage, prompts that worked): [`docs/00-process-and-assumptions.md`](docs/00-process-and-assumptions.md).

**One notable catch:** Perplexity fabricated verbatim Hacker News quotes and user handles that don't exist. A cross-checking subagent caught and discarded them before they reached the page. Lesson logged: always URL-verify VoC quotes.

---

## 4. Goals for the page

**Primary:** Convert Monetization/Growth PMs to self-serve "Start for free" signups. Every structural decision is justified by friction-removal or decision de-risking on the path to that action.

**Supporting goals:**
- Serve enterprise PMs in parallel via a co-located "Talk to sales" path, never making them hunt
- Defeat build-in-house as the real alternative (not named competitors), by conceding the 1% fee and reframing via opportunity cost and correctness
- Replace the current page's stale, feature-grid-heavy structure with a jobs-to-be-done narrative that lands for both SMB and enterprise from common ground

**Success signal:** self-serve signup conversion rate, segmented by SMB vs. enterprise referral source. Secondary: qualified sales requests. Page-health proxies: scroll-depth past the build-vs-buy section, interactive-demo engagement.

---

## 5. What was explicitly included and excluded

**Included (and why)**

- **Paywalls** (velocity wedge lead) — the brief's clearest claim: ship a paywall change with no app update, no designer, no release cycle. Made visual with a UI screenshot.
- **Experiments + predicted 12-month LTV winners** — the single clearest substance win over every competitor. A PM deciding mid-test on predicted long-term revenue, not lagging conversion, is a genuinely differentiated capability.
- **Charts / source of truth** — cross-platform entitlement substrate + 40+ integrations + Charts API answer the "does it plug into the stack we already run" question, which the live page mostly buries in the footer.
- **Web Billing (secondary)** — kept because the brief requires it and Floga's "six figures in a single day before their app was live" is a strong proof point. Not the lead.
- **Automated Refund Handler + Targeting** (brief's pain-to-answer mapping) — included within the source-of-truth and velocity sections as evidence, not as standalone feature callouts.
- **Build-vs-buy section** — the real alternative for this audience is "we'll build it in-house." Concede the fee, reframe via correctness (grace periods, receipt edge cases, maintain forever) and Floga's "3x the time."
- **Price-honest microcopy** ("Free until $2,500 in monthly tracked revenue") under every primary CTA — pre-empts the cost objection at the exact stall point.

**Excluded (deliberate cuts)**

- **5-persona router** — one sharp ICP beats a role-selector that dilutes PM focus and altitude
- **"Connect the SDK" / developer onboarding section** — wrong altitude for a PM page. Replaced with an ecosystem-fit section at PM altitude (SDKs + 40+ integrations as stack-fit reassurance, not setup instructions)
- **IAP-era 7-bullet feature grid** — the brief twice warns against feature laundry lists. Cut entirely.
- **Daily payouts** — no clear PM-level job tied to it
- **Self-reported scale as the headline stat** — no third party verifies RC's 106K apps / $14B tracked figures. Led with BCV's "~1/3 of new subscription apps" instead
- **5x "Learn more" CTAs** — replaced with action-bearing copy throughout ("Ship your first paywall free," "Run your first experiment free")

---

## 6. Key messaging

**The one idea:** Drive revenue at product speed.

RevenueCat is the one place a PM operates the whole revenue lever: ship changes on their own cadence, trust every number it produces, and decide on what's coming next.

**Three pillars (each is a PM job; features are evidence, not the story):**

1. **Velocity / Move your revenue, not your roadmap.** Ship pricing and packaging changes the moment you decide to, not next release. The paywall iteration no longer requires a designer, an engineering sprint, or an App Store review cycle. Lead proof: Pixelcut +16% from one A/B test; top-quartile apps gain +80% MRR vs. bottom-quartile at -33%.

2. **Source of truth / Quote every figure with confidence.** One view across iOS, Android, and web. Every entitlement, receipt, refund, and renewal resolved in one place. 40+ integrations mean your data is wherever your dashboards already are. First-party signal: "I barely look at the platform dashboards" (current RC customer, ICP interview).

3. **Forward-looking / Know the 12-month winner in week one.** Experiments surface predicted-LTV winners mid-test, not after 90 days of lagging conversion. Decide earlier, on what's going to happen, not what just happened. Proof: 55% of 3-day-trial cancellations happen on Day 0.

**Underneath all three (objection, not a pillar):** Concede the 1% fee. Reframe: receipts, refunds, renewals, and grace periods are solved. Paywalls and Web Billing come free on top of billing you would build anyway. The in-house path costs Floga "3x the time."

**Voice rule applied throughout:** verb-first, "you"-led, concrete capability, quantified payoff. "Change your paywall without shipping an app update." Lead emotional (relief from release-latency), close logical (the number).

---

## Links

- [Live site](https://revenuecat-three.vercel.app/)
- [Research evidence base](docs/fact-sheet.md)
- [Positioning and messaging brief](docs/05-positioning-and-narrative.md)
- [Conversion and CTA strategy](docs/06-conversion-and-cta.md)
- [Full process log and assumptions register](docs/00-process-and-assumptions.md)
- [Design tokens and visual system](design.md)

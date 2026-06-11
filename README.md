# RevenueCat PMM Take-Home

[![Live site](https://img.shields.io/badge/➜%20Live%20site-5B7FFF?style=for-the-badge&logoColor=white)](https://revenuecat-three.vercel.app/)

---

## AI tools

- **Claude Code (Opus 4.8)** — everything: research, synthesis, copy, code. Parallel subagent workflows ran research tracks concurrently.
- **Perplexity MCP** — citation-backed sourcing for competitor facts and market stats.
- **Chrome DevTools MCP** — measured design tokens from the live DOM. No guessing.
- **WebSearch / WebFetch** — live page teardown and competitor reads.

## Assumptions

| Assumption | Why |
|---|---|
| Hanken Grotesk + Inter instead of Object Sans | Object Sans is a paid font. Licensing violation to ship publicly. Near-identical substitute. |
| Velocity leads the narrative | Defeats build-in-house directly. Verified by brief and ICP interview ("move wayyy faster"). |
| Build-vs-buy is an objection, not a pillar | A pillar makes the page argue against a ghost. The brief says don't name competitors. |
| Audience narrowed to the Monetization/Growth PM | The brief's JTBD describes exactly this person. One sharp persona beats a 5-persona router. |
| "Start for free" is the primary CTA | The live page gates self-serve behind a demo request. RC is free to $2,500 MTR. No reason to gate. |
| BCV's "~1/3 of new subscription apps" leads scale | No third party verifies RC's self-reported 106K apps / $14B figures. Sourced stat is more credible. |
| Web Billing kept secondary | ICP interview: iOS/Android-only PM, zero web interest. Brief still requires it, so it earns a place. |
| Desktop-only | The brief's bar is a functional page on a 4-6 hr budget. Reviewer is on desktop. |

## Process

Research ran in parallel. Build was gated behind a committed positioning brief. No code was written until the messaging existed.

**Phase 1 — Research.** Three Claude Code subagent workflows ran concurrently across audience, product, competitive, teardown, and brand tracks. Perplexity MCP sourced stats. A live ICP interview with a current RC customer added first-party signal. Chrome DevTools MCP measured the live DOM. All findings went into [`docs/fact-sheet.md`](docs/fact-sheet.md).

**Phase 2 — Synthesis.** [Track 5](docs/05-positioning-and-narrative.md) consumed the fact-sheet and produced the messaging brief, 3 pillars, section arc, and cut-list. That resolved the build gate. [Track 6](docs/06-conversion-and-cta.md) mapped CTAs and objection placement.

**Phase 3 — Build.** Single static page, Tailwind, no framework. Deployed to Vercel.

One catch: Perplexity invented Hacker News quotes and user handles that don't exist. A cross-checking subagent caught them. Nothing fabricated reached the page.

Full log: [`docs/00-process-and-assumptions.md`](docs/00-process-and-assumptions.md)

## Page goal

Get Monetization/Growth PMs to sign up for free. Every decision removes friction or de-risks the moment before that action.

Secondary: a co-located "Talk to sales" path for enterprise, never buried. The page should make building in-house feel like the slower, riskier choice.

## Included / excluded

**In**
- Paywalls — the velocity lead. Ship a change with no app update, no designer, no release cycle.
- Experiments + predicted 12-month LTV — the clearest substance win. Decide on future revenue, not past conversion.
- Charts + 40+ integrations — answers "does this fit our stack," which the live page buries in the footer.
- Build-vs-buy section — concede the 1% fee, reframe via correctness and Floga's "3x the time."
- Price microcopy under every CTA — "Free until $2,500 in monthly tracked revenue."
- Web Billing (secondary) — brief requires it. Floga proof is strong.

**Out**
- 5-persona router — dilutes focus.
- Developer onboarding section — wrong altitude. Replaced with ecosystem-fit at PM level.
- IAP feature grid — a laundry list. Cut.
- Daily payouts — no PM-level job attached.
- Self-reported scale as the headline — no independent verification. Used BCV's sourced stat instead.
- 5x "Learn more" CTAs — replaced with action-bearing copy.

## Key messaging

**One idea:** Drive revenue at product speed.

**Three pillars:**

1. **Velocity.** Ship pricing changes the moment you decide to, not next release. Proof: Pixelcut +16% from one A/B test.
2. **Source of truth.** One view across iOS, Android, and web. 40+ integrations. "I barely look at the platform dashboards" (ICP interview).
3. **Forward-looking.** Know the 12-month winner in week one. Predict LTV mid-experiment, not after 90 days of lag.

Build-vs-buy runs underneath all three. Concede the fee. Reframe: receipts, refunds, and renewals are solved. Paywalls come free on top of billing you would build anyway.

Voice: verb first, "you"-led, quantified. "Change your paywall without shipping an app update."

---

[Research](docs/fact-sheet.md) · [Messaging brief](docs/05-positioning-and-narrative.md) · [CTA strategy](docs/06-conversion-and-cta.md) · [Process log](docs/00-process-and-assumptions.md) · [Design tokens](design.md)

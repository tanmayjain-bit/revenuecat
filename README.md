# RevenueCat PMM Take-Home

[![Live site](https://img.shields.io/badge/➜%20Live%20site-5B7FFF?style=for-the-badge&logoColor=white)](https://revenuecat-three.vercel.app/)

I treated this as a positioning problem first. No code was written until the messaging existed.

---

## AI tools

- **Claude Code (Opus 4.8)**: the primary tool for everything. Research ran as parallel subagent workflows: multiple Claude agents worked simultaneously, each focused on one area (audience, competitors, live page teardown, brand tokens). They fed findings into a shared evidence base. A separate synthesis agent then collapsed those findings into a positioning brief. Only after that was code written.
- **Perplexity MCP**: citation-backed sourcing for competitor facts and market stats.
- **Chrome DevTools MCP**: measured design tokens directly from the live DOM. No guessing from screenshots.
- **WebSearch / WebFetch**: live page teardown and competitor reads.

## Assumptions

| Assumption | Why | What changes if wrong |
|---|---|---|
| Velocity leads the narrative | Defeats build-in-house directly. Verified by brief and user interview ("move wayyy faster"). | Pillars re-order; section inventory stays the same. |
| Build-vs-buy is an objection, not a pillar | A pillar makes the page argue against a ghost. The brief says don't name competitors. | Promote to its own section if testing shows it needs more weight. |
| Audience narrowed to the Monetization/Growth PM | The brief's jobs-to-be-done describes exactly this person. One sharp persona beats a 5-persona router. | Broaden hero copy; structure holds. |
| "Start for free" is the primary CTA | The live page gates self-serve behind a demo request. RC is free to $2,500 MTR. No reason to gate. | Swap CTA priority based on conversion data. |
| BCV's "~1/3 of new subscription apps" leads scale | No third party verifies RC's self-reported 106K apps / $14B figures. Sourced stat is more credible. | Self-reported figures are ready as a swap. |
| Web Billing kept secondary | User interview: iOS/Android-only PM, zero web interest. Brief still requires it, so it earns a place. | Promote if the target audience tilts toward web-to-app funnels. |
| Desktop-only | The brief's bar is a functional page on a 4-6 hr budget. Reviewer is on desktop. | A static Tailwind page is straightforward to make responsive as an additive pass. |

## Process

Research ran in parallel. No code was written until the messaging existed.

**Phase 1: Research.** Parallel Claude subagents ran across five areas at once: audience, product, competitors, live page teardown, and brand. Perplexity MCP sourced stats with citations. A user interview with Tanmay Jain, a Monetization PM and current RevenueCat customer, added first-party signal. Chrome DevTools MCP measured the live DOM. All findings went into [`docs/fact-sheet.md`](docs/fact-sheet.md).

**Phase 2: Synthesis.** [Track 5](docs/05-positioning-and-narrative.md) consumed the evidence base and produced the messaging brief, 3 pillars, section arc, and cut-list. [Track 6](docs/06-conversion-and-cta.md) mapped CTAs and objection placement.

**Phase 3: Build.** Single static page, Tailwind, no framework. Deployed to Vercel.

Full log: [`docs/00-process-and-assumptions.md`](docs/00-process-and-assumptions.md)

## Ideation

The research kept surfacing three PM frustrations: they couldn't ship changes fast enough, they didn't trust their numbers across platforms, and they were making bets on data that was already stale. Those became the three pillars. The umbrella line, "Drive revenue at product speed," collapsed all three into one idea: the revenue lever exists, but PMs can't move it at product speed. Features were then mapped as evidence for each pillar rather than listed as a set.

## Pivots

- **Web Billing demoted.** Started as a co-equal feature. The user interview surfaced an iOS/Android-only PM with zero web interest, so it became secondary. The brief still requires it, so it earns a section, not the lead.
- **Build-vs-buy became an objection, not a pillar.** Early positioning drafts treated it as a standalone argument. Synthesis showed that elevating it makes the page argue against a ghost. Woven underneath all three pillars instead, with a concede-then-reframe beat.
- **Scale stat switched.** Planned to lead with RC's self-reported 106K apps / $14B tracked revenue. Research found no third party verifies those figures. Swapped to BCV's sourced "~1/3 of new subscription apps."
- **CTA flipped.** The live page leads with "Request a demo." Auditing the conversion logic showed that gates self-serve behind a sales call with no commercial reason to do so. "Start for free" became primary; demo became tertiary.
- **Perplexity fabricated customer quotes.** A verification agent found Perplexity invented Hacker News users and quotes that don't exist. All fabricated material was discarded before reaching the page.

## Page goal

Get Monetization/Growth PMs to sign up for free. Every decision removes friction or de-risks the moment before that action.

Secondary: a co-located "Talk to sales" path for enterprise, never buried.

## Included / excluded

**In**
- Paywalls: the velocity lead. Ship a change with no app update, no designer, no release cycle.
- Experiments + predicted 12-month LTV: the clearest substance win. Decide on future revenue, not past conversion.
- Charts + 40+ integrations: answers "does this fit our stack," which the live page buries in the footer.
- Build-vs-buy section: concede RC's 1% fee, reframe via correctness and Floga's "3x the time."
- Price microcopy under every CTA: "Free until $2,500 in monthly tracked revenue."
- Web Billing (secondary): brief requires it. Floga proof is strong.

**Out**
- 5-persona router: dilutes focus.
- Developer onboarding section: wrong altitude. Replaced with ecosystem-fit at PM level.
- IAP feature grid: a laundry list. Cut.
- Daily payouts: no PM-level job attached.
- Self-reported scale as the headline: no independent verification. Used BCV's sourced stat instead.

## Key messaging

Full positioning brief: [`docs/05-positioning-and-narrative.md`](docs/05-positioning-and-narrative.md)

**One idea:** Drive revenue at product speed.

**Three pillars:**

1. **Velocity.** Ship pricing changes the moment you decide to, not next release. Proof: Pixelcut +16% from one A/B test.
2. **Source of truth.** One view across iOS, Android, and web. 40+ integrations. "I barely look at the platform dashboards" (user interview).
3. **Forward-looking.** Know the 12-month winner in week one. Predict LTV mid-experiment, not after 90 days of lag.

Build-vs-buy runs underneath all three. Concede RC's 1% fee. Reframe: receipts, refunds, and renewals are solved. Paywalls come free on top of billing you would build anyway.

Voice: verb first, "you"-led, quantified. "Change your paywall without shipping an app update."

---

[Research](docs/fact-sheet.md) · [Messaging brief](docs/05-positioning-and-narrative.md) · [CTA strategy](docs/06-conversion-and-cta.md) · [Process log](docs/00-process-and-assumptions.md) · [Design tokens](design.md)

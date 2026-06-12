# RevenueCat PMM Take-Home

<a href="https://revenuecat-three.vercel.app/"><img src="https://img.shields.io/badge/➜%20Live%20site-F2545B?style=for-the-badge&logoColor=white" height="40"/></a>

I treated this as a positioning problem first. I wrote no code until the messaging existed.

---

## AI tools

- **Claude Code (Opus 4.8)**: my primary tool throughout. I ran research as parallel subagent workflows, multiple agents each scoped to one area (audience, competitors, live page teardown, brand tokens). They fed into a shared evidence base. A synthesis agent collapsed the findings into a positioning brief. Only after that did I write code.
- **Perplexity MCP**: citation-backed sourcing for competitor facts and market stats.
- **Chrome DevTools MCP**: I measured design tokens directly from the live DOM. No guessing from screenshots.
- **WebSearch / WebFetch**: live page teardown and competitor reads.

## Assumptions

| Assumption | Why | What changes if wrong |
|---|---|---|
| Velocity leads the narrative | Defeats build-in-house directly. Verified by brief and user interview ("move wayyy faster"). | Pillars re-order; section inventory stays the same. |
| Build-vs-buy is an objection, not a pillar | A pillar makes the page argue against a ghost. The brief says don't name competitors. | Promote to its own section if testing shows it needs more weight. |
| Audience narrowed to the Monetization/Growth PM | The brief's jobs-to-be-done describes exactly this person. One sharp persona beats a 5-persona router. | Broaden hero copy; structure holds. |
| "Start for free" is the primary CTA | The live page gates self-serve behind a demo request. RC is free to $2,500 MTR. No reason to gate. | Swap CTA priority based on conversion data. |
| BCV's "~1/3 of new subscription apps" leads scale | No third party verifies RC's self-reported 106K apps / $14B figures. Sourced stat is more credible. | Self-reported figures are ready as a swap. |
| Case study stats from revenuecat.com/testimonials | The brief only names Floga. ElevenLabs, Runna, Ladder, and Pixelcut were verified against RC's testimonials page and individual case study URLs before use. | Swap to next verified stat if RC removes a case study. |
| Web Billing kept secondary | User interview: iOS/Android-only PM, zero web interest. Brief still requires it, so I gave it a place. | Promote if the target audience tilts toward web-to-app funnels. |
| Desktop-only | The brief's bar is a functional page on a 4-6 hr budget. Reviewer is on desktop. | Easy to make responsive later. |

## Process

The brief described the audience precisely: PMs who own user experience and product strategy, care about aligning monetization with user value, and feel the pain when they cannot move fast. They are not writing billing code. They are waiting on someone who is.

I started with research before touching a single line of copy. I ran parallel Claude subagents across five areas: audience, product, competitors, live page teardown, and brand. Perplexity MCP sourced cited stats. I interviewed Tanmay Jain, a Monetization PM and active RevenueCat customer, to get a real customer's perspective. I measured the live DOM with Chrome DevTools MCP. Everything went into [`docs/fact-sheet.md`](docs/fact-sheet.md).

With that base, I moved to synthesis. The rule I set for myself: every feature had to earn its place by answering a specific PM job. Paywalls answer "I want to test pricing but I can't wait for engineering." Predicted LTV answers "I want to call a winner before the experiment runs for 90 days." Features without a clear job, I cut. That produced the messaging brief, 3 pillars, section arc, and deliberate cut-list in [Track 5](docs/05-positioning-and-narrative.md). [Track 6](docs/06-conversion-and-cta.md) mapped CTAs and objection placement.

Then I built. Single static page, Tailwind, no framework. Deployed to Vercel.

Full log: [`docs/00-process-and-assumptions.md`](docs/00-process-and-assumptions.md)

## Ideation

Three PM frustrations kept showing up: they couldn't ship changes fast enough, they didn't trust their numbers across platforms, and they were making bets on stale data. Those became my three pillars. The line I landed on, "Drive revenue at product speed," collapses all three. I mapped features as evidence for each pillar, not as a list.

The frustration underneath all three is the same: PMs feel gated by engineers. Every paywall change, every pricing test needs a ticket, a sprint, a release. I lead with that relief.

I ordered sections to follow the buyer's mental journey. Velocity comes first because it is the sharpest, most universal pain. Source of truth follows, because a PM who believes they can ship faster will immediately ask "but will my numbers be reliable?" Forward-looking closes the product story, because predicted LTV is the most differentiated claim. Social proof and Web Billing follow: proof the platform is trusted at scale, then the commission angle for the PM who is already sold on the core.

## Pivots

- **Web Billing demoted.** I started with it as a co-equal feature. Then I interviewed an iOS/Android-only PM with zero web interest. I demoted it to secondary. The brief requires it, so it earns a section, not the lead.
- **Build-vs-buy became an objection, not a pillar.** I initially gave it its own section. That much space made the page feel defensive. A smart PM's first instinct is "can we build this?" Better to concede RC's 1% fee honestly, reframe quickly, and keep moving. I embedded that underneath all three pillars instead.
- **Scale stat switched.** I planned to lead with RC's self-reported 106K apps / $14B tracked revenue. I found no third party verifying those numbers. I swapped to BCV's sourced "~1/3 of new subscription apps."
- **CTA flipped.** The live page leads with "Request a demo." That is a sales gate with no reason to exist for a product that is free to $2,500 MTR. I made "Start for free" primary and kept demo as a tertiary option for enterprise.
- **Perplexity fabricated customer quotes.** A verification agent I ran found Perplexity had invented Hacker News users and quotes that do not exist. None of it reached the page.

## Page goal

Get Monetization/Growth PMs to sign up for free.

Secondary: a "Talk to sales" option for enterprise, always visible next to the primary CTA.

## Included / excluded

**In**
- Paywalls: the velocity lead. Ship a change with no app update, no designer, no release cycle.
- Experiments + predicted 12-month LTV: the clearest substance win. Decide on future revenue, not past conversion.
- Charts + 40+ integrations: answers "does this fit our stack," which the live page buries in the footer.
- Build-vs-buy section: I concede RC's 1% fee, then reframe via correctness and Floga's "3x the time."
- Price microcopy under every CTA: "Free until $2,500 in monthly tracked revenue."
- Web Billing (secondary): the brief requires it. Floga's proof is strong.

**Out**
- 5-persona router: I cut this to keep focus. One sharp persona beats a router.
- Developer onboarding section: wrong altitude for a PM audience. I replaced it with a section on what RC integrates with.
- IAP feature grid: a laundry list. The brief explicitly penalizes this. Cut.
- Daily payouts: finance and founder audience, not PM. Cash flow timing is a CFO or bootstrapped-founder concern. A PM optimizing conversion and retention has no job here.
- Self-reported scale as the headline: I found no independent verification. I used BCV's sourced stat instead.
- Web Billing and Web-to-App Funnels from the feature bento: Web Billing already has its own proof section (Floga); I deprioritized Funnels based on the user interview. I kept the bento to 4 cards: Paywalls, Experiments, Targeting, Charts.

## Key messaging

Full positioning brief: [`docs/05-positioning-and-narrative.md`](docs/05-positioning-and-narrative.md)

**One idea:** Drive revenue at product speed.

**Three pillars:**

1. **Velocity.** Ship pricing changes the moment you decide to, not next release. Proof: Pixelcut +16% from one A/B test.
2. **Source of truth.** One view across iOS, Android, and web. 40+ integrations. "I barely look at the platform dashboards" (user interview).
3. **Forward-looking.** Know the 12-month winner in week one. Predict LTV mid-experiment, not after 90 days of lag.

I run build-vs-buy underneath all three. The real alternative for this audience is not a named competitor, it is "we'll build it in-house." I concede RC's 1% fee, then reframe: receipts, refunds, and renewals are solved. Paywalls come free on top of billing you would build anyway.

Voice: verb first, "you"-led, quantified. "Change your paywall without shipping an app update."

---

[Research](docs/fact-sheet.md) · [Messaging brief](docs/05-positioning-and-narrative.md) · [CTA strategy](docs/06-conversion-and-cta.md) · [Process log](docs/00-process-and-assumptions.md) · [Design tokens](design.md)

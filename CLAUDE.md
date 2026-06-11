# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this project is

A take-home assignment for a **Product Marketing Manager (PMM)** role at RevenueCat: ship an **updated "For Product" landing page** targeting **Product Managers**, refreshing the messaging and feature narrative on the current (stale) page → https://www.revenuecat.com/for-product/

The work is judged as **product marketing, not engineering**. The bar is narrative/positioning quality, visual storytelling, and demonstrated AI fluency — not code sophistication. Budget ~4–6 hours. Source of truth is `Take-Home Assignment - PMM at RevenueCat.pdf` — re-derive from it when in doubt.

## Current status (2026-06-11)

**All tracks complete. Page built and deployed.** All research tracks (1–4, 7, 8) are done, the fact-sheet is populated, Track 5 messaging brief + pillars are committed (build gate resolved), Track 6 CTA strategy is locked, and Track 9 has scaffolded and shipped `site/index.html` + `site/styles.css` to Vercel. Two visual placeholders remain in the Velocity and Source-of-truth sections pending screenshot replacement (tracked in `CHECKLIST.md`). Track 0 process log is current.

## Hard constraints (do not violate)

- **No no-code site builders** — Squarespace, Wix, Webflow are explicitly disallowed. Build with code; AI-assisted tools are required (v0, Bolt, Replit, Cursor/Copilot, Claude).
- Work must be original; no outsourcing.
- Deliver a **functional, deployable** page (Vercel/Netlify/built-in hosting). Deployability is part of the deliverable.
- Deliver a **separate process write-up** (research, ideation, iteration, AI usage). Graded — maintained continuously in Track 0, not reconstructed at the end.

## Brief canon (precise facts from the PDF — the source of truth)

The reviewer indexes against the brief. Full verbatim canon + per-claim sourcing lives in **`docs/fact-sheet.md` §0**; the precise essentials:

**The 4 legacy use cases** (brief says *"still relevant and important"* — keep, don't discard): reduce engineering time on maintenance/monetization changes · reduce multi-platform complexity · single *"source of truth"* of monetization data & reporting · improve conversion by A/B testing pricing/packaging/paywalls.

**The 5 "What's New" product areas** (exact names; *inputs, not a checklist* — the brief twice forbids a laundry list):
- **Paywalls** — remote, no-code config of the *entire* paywall with no code/app update; drag-and-drop, AI generation, custom runtime variables, Figma export, branding system; GA on iOS/Android/RN/Flutter/web. *Key insight: "paywall iteration no longer requires a designer, engineering sprint or an App Store review cycle."*
- **Web-to-App Funnels** — no-code web→app onboarding funnels with branching, a web checkout (RevenueCat Billing or Paddle), per-step analytics + UTM.
- **Charts** — LTV Prediction + Cohort Explorer (trials now included), 4 real-time paywall-performance charts, Charts API, Apple Search Ads segmentation.
- **Web Billing (RevenueCat Billing)** — web purchases (Stripe, Apple/Google Pay, multi-currency) that auto-unlock in-app entitlements via Redemption Links; bypasses the *"15-30%"* store commission; **Floga proof = "six figures in a single day before their app was live"** (use the brief's "six figures," not the web "$120K").
- **Experiments** — multivariate A/B/C/D, **predicted 12-month LTV winners** (forward-looking, mid-experiment), one-action winner rollout, draft mode.

**The brief's pain → answer mapping** (use these pairings exactly): eng bottleneck on paywall changes → Paywalls (no app update) · experimentation uncertainty → predicted 12-mo LTV winners · platform policy volatility & refund abuse → **Automated Refund Handler** · one-size-fits-all monetization → **Targeting rules engine** + Web Funnels branching · acquisition→revenue attribution blind spots → Funnels analytics (UTM) + Charts API · app-store commission pressure → Web Billing · late detection of issues → paywall-performance charts + LTV prediction.

**Audience (verbatim JTBD):** PMs *"own user experience and product strategy… care about aligning monetization with user value, iterating quickly without shipping constant releases… typically not the ones writing billing code, but… feel the pain when they cannot move fast."* Serve **both enterprise and SMB**.

**Deliverables/logistics:** (1) functional deployable page; (2) separate AI-process + assumptions doc (this repo's `docs/` + Track 0). Share via live link (Vercel/Netlify) or project link (Replit/Bolt/v0). $30 stipend, ~4–6 hrs.

## Repo architecture

The project runs as parallel **tracks**, each owning one doc under `docs/`. The dependency order (who feeds whom) is the flow diagram below; the page is built only after the synthesis track (5) resolves.

```
revenuecat/
├── CLAUDE.md                          ← this file: orchestration + constraints + track map
├── Take-Home Assignment ….pdf         ← original brief (source of truth)
├── design.md                          ← BUILD-FACING quick-ref: paste-ready tokens + component recipes (mirrors docs/08)
├── docs/                               ← one file per track (the thinking)
│   ├── 00-process-and-assumptions.md   Track 0  Process & assumptions log  (cross-cutting)
│   ├── 01-audience-research.md         Track 1  PM/PGM personas + JTBD + pains
│   ├── 02-product-context.md           Track 2  RevenueCat features / what shipped
│   ├── 03-competitive-and-build-vs-buy.md  Track 3  Competitors + build-vs-buy
│   ├── 04-current-page-teardown.md     Track 4  Baseline audit of live page
│   ├── fact-sheet.md                   ⭐ Consolidated evidence base (§0 brief-canon + §A–J research) → feeds Track 5
│   ├── 05-positioning-and-narrative.md Track 5  ⭐ Messaging brief + pillars, arc, cut-list (synthesis)
│   ├── 06-conversion-and-cta.md        Track 6  CTA / funnel strategy
│   ├── 07-proof-and-credibility.md     Track 7  Stats, logos, case studies
│   ├── 08-brand-voice-and-visual-system.md  Track 8  Visual identity + copy voice (measured-from-live tokens)
│   ├── 08-5-tech-stack.md              Track 8.5  Live-page tech-stack teardown → informs the build stack
│   └── 09-build-deploy-qa.md           Track 9  Build, deploy, QA
└── site/                               ← the landing page code (scaffolded in Track 9)
```

## Dependency flow (work in this order)

```
RESEARCH (parallel)                SYNTHESIS              EXECUTION
 1 Audience ─┐
 2 Product ──┤
 3 Competitive ──┼──►  5 Positioning ⭐ ──►  6 Conversion ──►  9 Build/Deploy/QA
 4 Teardown ─┤              ▲
 7 Proof ────┤              │
 8 Brand ────┘              │
                            └── consumes all research

 0 Process & assumptions  ─── cross-cutting, append throughout ───────────────►
```

**The rule that matters:** do **not** start building (`site/`) until Track 5 has a committed **messaging brief + messaging pillars** (the synthesis artifact — Name/Audiences/Value props[Primary·Secondary·Bonus]/Goal, plus 3–4 pillars), a section arc, and a cut-list. Building before synthesizing produces the feature laundry list the brief explicitly penalizes.

## Subagent dispatch & the Question-Exhaustion Map

**Dispatch rule (how to run a track):** spawn a fresh subagent given **only** (a) the track's job as its instructions, (b) the *contents* of the upstream artifacts it depends on (per the flow diagram above), and (c) the global constraints in this file. It writes its single doc under `docs/`. Before marking a track done, confirm its sections are real (not placeholders). Don't dispatch a track until the tracks it depends on are done — this keeps Track 5 from synthesizing on incomplete research and prevents the feature-laundry failure mode. Each subagent sees only its declared inputs: this boxing is the mechanism that forces synthesis over enumeration. **Build gate:** `site/` work cannot begin until Track 5's messaging brief + pillars exist.

**Question-Exhaustion Map:** Track 1 produces a PM question chain (immediate · decision-stage · objection · comparison · edge-case). Track 5 must answer every question in the chain (coverage requirement) and Track 6 places objection answers near the relevant CTA. An unanswered objection — especially build-vs-buy — is the reader leaving for a competitor or for "we'll build it in-house."

## Core messaging principles (always apply)

- **Lead with jobs-to-be-done, not features.** PMs own UX/strategy and feel the pain when they can't move fast; they typically don't write billing code.
- **Synthesize, don't enumerate.** Merge old + new capabilities into one cohesive story positioning RevenueCat as a complete monetization solution for PMs. Deliberately leave features out — record the cuts.
- **Translate every feature into PM value** (feature → benefit → job done) with strong information hierarchy.
- **Answer build-vs-buy.** The real alternative for this audience is "we'll build it in-house" — the page should implicitly defeat that.
- **Serve enterprise *and* SMB** PMs.
- **Confident assumptions backed by reasoning;** don't spiral on being "right" (log assumptions in Track 0).
- **Feel "RevenueCat-ish"** — brand-aware, not pixel-perfect.

**The 3 differentiation wedges (research converged here — `docs/fact-sheet.md` §F):**
1. **Velocity / independence** — *"ship monetization without shipping code"* (lead with this; defeats build-in-house; rests on the brief-verified Paywalls claim).
2. **Completeness / source-of-truth** — *"paywalls are the surface; entitlements are the source of truth."* Every rival is partial; even Superwall now *claims* "source of truth" while routing billing through a backend like RC's. Own the only definition that includes billing, receipts, refunds, grace periods, and cross-platform/web entitlements.
3. **Forward-looking intelligence** — decide on **predicted LTV**, not lagging conversion (clearest substance win over Adapty/Superwall).

**Do NOT name competitors on the page** — wedges sharpen RC's own story, not a comparison. The page must implicitly defeat **build-vs-buy** (the real alternative is "we'll build it in-house"); the honest 1%-fee / "I could build it myself" objection should be **conceded then reframed** via the edge-case correctness checklist (`docs/fact-sheet.md` §E/§G-VoC).

## Brand, voice & build stack (distilled — full refs linked)

Tokens were **measured from the live `/for-product/` DOM** (2026-06-06), not guessed. **Build from [`design.md`](design.md)** (paste-ready `:root` tokens + component recipes); rationale/voice/licensing live in [`docs/08`](docs/08-brand-voice-and-visual-system.md); the stack decision is in [`docs/08-5-tech-stack.md`](docs/08-5-tech-stack.md).

**Visual DNA:** white + **ink-navy `#1F1F47`** base, color as *accent not wash* → **indigo `#576DDB`** = every CTA/link, **coral `#F2545B`** = one highlight + key stat numbers, **green `#11D483`** = positive signals only. **Full-pill** buttons/chips, **20px** soft cards, **two-up alternating** sections, generous whitespace/vertical rhythm. Signature visual = **icon-coin → dotted-line → RC-hexagon** flow diagram (build it as ad → funnel → checkout → redemption).

**Fonts (licensing):** RC's **Object Sans is paid — do NOT ship it.** Use **Hanken Grotesk** (headings) + **Inter** (body), both Google Fonts, deployable.

**Voice:** verb-first / "you"-led → concrete capability → **quantified** payoff (*"Change your paywall without shipping an app update"*). **Do:** conversion/LTV/retention/ARR/churn, "no engineering required," "on your own cadence," named proof. **Don't:** growth/synergy/revolutionary/seamless/unlock/supercharge, unquantified AI hype, a feature named without its benefit. Lead emotional (relief), close logical (the number).

**NO EM DASHES in any page copy or deliverable text.** Never use `—` in headlines, body copy, CTAs, or marketing text. Use a comma, a period, or two separate sentences instead. (This rule applies to copy that ships; internal docs/notes are exempt but prefer commas/periods there too.)

**Stack decision (Track 8.5 → 9):** deliberately **lean** — a **single static page** under `site/`, **Tailwind + the brand tokens**, self-hosted/Google fonts. **Drop** Next.js/router, any CMS (hardcode copy from Track 5/7), i18n, and analytics — all over-engineering for one landing page. **Deploy to Vercel** (the live RC site runs on Netlify; Vercel is our pick purely for friction-free hosting).

## Build commands

_Not yet scaffolded._ Stack is decided ([`docs/08-5`](docs/08-5-tech-stack.md)): single static page + Tailwind, no framework, deploy to Vercel. When Track 9 scaffolds `site/`, replace this section with the real `dev` / `build` / `lint` / deploy commands and record the live URL in `docs/09-build-deploy-qa.md`.

## Working conventions

- **Synthesis & build run sequentially, one track at a time** (Track 5 → 6 → 9), so each can be reviewed and steered. **Research tracks (1–4, 7) were deepened via parallel subagent workflows** at the user's direction — the orchestrator synthesizes their structured findings into the fact-sheet (boxing still forces synthesis over enumeration). Keep findings visible by restating them in the main session.
- **Respect the dependency order.** Before starting a track, confirm the tracks it depends on (per the flow diagram) are done and real. Don't dispatch downstream of incomplete research.
- **Sourcing:** Perplexity MCP is the citation-backed research tool (stats, market data, competitor facts) for Tracks 2/3/7; WebSearch/WebFetch for the live page and general lookups. Log each use in Track 0.
- Treat each `docs/NN-*.md` as the living home for that track's thinking; update it as you learn.
- **Log every assumption as you make it** in `docs/00-process-and-assumptions.md` — append to the **Assumptions register** (assumption · why reasonable · what changes if wrong) the moment a decision is made, never reconstructed at the end. This is non-negotiable: 00 is a graded deliverable and the brief explicitly rewards "confident assumptions backed by reasoning." After advancing any track, audit it for unlogged assumptions and backfill 00.
- Log every meaningful decision, pivot, and prompt in `docs/00-process-and-assumptions.md` as you go — it's a graded deliverable. **Maintain the Tooling log table** there: record which AI tool/model was used for what and how.
- Verify product claims against the brief PDF before they reach the page.
- Reference the live page and RevenueCat brand before designing.

## Writing standard

All copy — README, page text, process docs — should follow this principle:

> **The Day You Became A Better Writer** — Scott Adams
>
> Business writing is about clarity and persuasion. The main technique is keeping things simple. Simple writing is persuasive. A good argument in five sentences will sway more people than a brilliant argument in a hundred sentences.
>
> Simple means getting rid of extra words. Don't write "He was very happy" when you can write "He was happy." You think the word "very" adds something. It doesn't. Prune your sentences.
>
> Your first sentence needs to grab the reader.
>
> Write short sentences. Avoid putting multiple thoughts in one sentence.
>
> Learn how brains organize ideas. Readers comprehend "the boy hit the ball" quicker than "the ball was hit by the boy." Both sentences mean the same, but it's easier to imagine the object before the action. All brains work that way.

Apply this to every deliverable. If a sentence can be cut, cut it. If a word can be removed, remove it. Short is persuasive. Long is noise.

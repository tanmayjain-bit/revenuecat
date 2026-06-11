# Outstanding Work – RevenueCat PMM Take-Home

## Immediate Work (in order)

- [ ] **Track 2 Review: Product Context** – Review claims against brief PDF, verify accuracy

- [ ] **Track 9: Build & Deploy** – Site scaffold under `site/`, Tailwind + tokens, deploy to Vercel  
  _Consumes: Track 5 (messaging), Track 6 (CTA), Track 8 (design.md tokens)_

- [ ] **Track 0 Final Audit** – Backfill any missing assumptions/tooling log entries

## Deliverables & Documentation

- [ ] **README.md** – Submission entry point with live link, 2–3 sentence brief on what this is  
  _(Not graded, but required for clarity)_

- [ ] **Submission package** – Verify all pieces are present:
  - [ ] `docs/00-process-and-assumptions.md` – Tooling log + assumptions register up-to-date
  - [ ] `docs/01–08-*.md` – All research tracks complete and non-placeholder
  - [ ] `docs/fact-sheet.md` – Consolidated evidence (§0 + §A–J) ready for review
  - [ ] `docs/05-positioning-and-narrative.md` – Messaging brief + pillars present
  - [ ] `design.md` – Paste-ready tokens + component recipes (mirrors Track 8)
  - [ ] `site/` – Deployable code, responsive, matches visual tokens
  - [ ] Live Vercel URL – functional, no 404s, all CTAs clickable

## Visuals to source (two placeholder divs in site/index.html)

- [ ] **Section 5 (Velocity) visual** – Replace `<div class="visual-ph">Paywall editor...</div>` with a screenshot of the RC no-code paywall builder. Source: revenuecat.com, the RC dashboard, or their press kit. A drag-and-drop editor screenshot is the most persuasive visual for the velocity claim.
- [ ] **Section 6 (Source of truth) visual** – Replace `<div class="visual-ph">"One truth → many tools"...</div>` with a hub-and-spoke diagram or the RC Charts dashboard screenshot. Alternatively, a grid of integration logos (Amplitude, Mixpanel, Braze, BigQuery) with the RC hexagon at the center makes the "40+ integrations" claim visual.

## Quality & Nits

- [ ] **Copy review** – No em dashes (`—`), all features → benefits → jobs, verify claims vs. brief PDF
- [ ] **Design nits** – Color usage (indigo for CTA, coral for stats/highlight, green for positive), full-pill buttons, 20px cards, icon-coin→dotted-line→hexagon visible
- [ ] **Brand voice** – Verb-first, quantified payoffs, no unqualified AI hype, concrete capabilities
- [ ] **Responsive check** – Mobile, tablet, desktop all readable; CTAs tap-friendly
- [ ] **Process doc (Track 0) final review** – Assumptions backfilled, decisions logged, no gaps

## Notes

- **Build gate:** Do not scaffold `site/` until Track 5 (messaging brief + pillars) is done.
- **Dependencies:** 5 → 6 → 9 are sequential; run one at a time + review between each.
- **Graded deliverables:** Process doc (Track 0) + live page + all research tracks.
- **Live page must deploy to Vercel** (not Netlify, not local). Share the live URL in README.

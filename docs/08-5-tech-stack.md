# Track 8.5 — Build Stack (lean static mockup)

**Job:** Pick the stack for a single take-home landing page — code-based (the brief forbids no-code builders), RevenueCat-ish, no over-engineering.

**Context:** the live `/for-product/` page is a large, CMS-driven, multi-locale marketing site (Next.js + Tailwind + Sanity, Netlify/CloudFront, i18n, GTM/Segment). Almost all of that stack exists to serve hundreds of editor-managed pages in many languages — none of which a one-page mockup needs. So we mirror only the styling DNA and drop the rest.

## Recommended stack
- **A single static page** under `site/` — `index.html` (or a Vite static scaffold for hot-reload + an easy build step). No router, no React app shell, no server runtime.
- **Tailwind CSS** carrying Track 8's design tokens (brand colors, spacing, type scale) via `tailwind.config`. Build with the Tailwind CLI (or the Vite Tailwind plugin) to emit one static stylesheet.
- **Self-hosted brand fonts** (Helvetica Neue body + a geometric display face à la Object Sans), loaded with `@font-face`.
- **Static content** — copy/proof hardcoded from Tracks 5/7; images as local optimized assets.
- **Deploy to Vercel** — instant public URL, zero config. (RevenueCat itself runs on Netlify; Vercel is our pick purely for friction-free hosting.)

## Mirror vs. drop
- ✅ **Mirror:** Tailwind with a brand-tokened theme; self-hosted brand fonts. These give the RevenueCat-ish look and satisfy "build with code."
- ❌ **Drop (over-engineering for one static page):** Next.js / any framework router; Sanity / any CMS (hardcode copy); i18n / locale routing (English-only); multi-host layering (pick one); GTM / Segment / pixels (no analytics requirement).

> **For Track 9:** update CLAUDE.md's "Build commands" with the real `dev`/`build`/`lint` once `site/` is scaffolded, and record the chosen host + live URL in `09-build-deploy-qa.md`.

# PR Influencer — prinfluencer.net (static landing site)

The influencer PR service brand of **influUGC**. Built Nov 5, 2026. **Files only — not deployed.**

## ⚠️ Design direction (owner change, Nov 5, 2026 — 23:57)

This site was first drafted in a distinct editorial/PR identity (off-white + press
red). The owner superseded that the same night: **ALL network satellite sites now
use the main influUGC identity**. The site was fully restyled before delivery:

- Black background `#000`, neon lime accent `#C8FF00`, dark panels, bold heavy
  typography — the www.influugc.com feel.
- Brand lockup: `PR Influencer.` wordmark with the subline "The influencer PR
  service of influUGC" (Arabic: «خدمة العلاقات العامة بالمؤثرين من influUGC»).
- Only real company data: est. 2020, Arab League St Agouza (Giza 12651),
  Egypt + Saudi/Gulf, real client names (Riyadh Season, Saudi Tourism Authority,
  flynas, Saudia, realme, Domino's, TikTok Live, Zanussi). No prices, no invented
  figures, no testimonials, no stock imagery (CSS/text only).

## Pages built (3 HTML pages, 2 languages)

| File | What |
|---|---|
| `index.html` | Arabic-first landing (RTL): hero, client proof strip, **guides section (3 guides, see retrofit note below)**, 5 services (influencer PR campaigns, creator relations, product seeding, event invitations, brand trips), why influUGC (with the in-body editorial link to influugc.com), 4-step process, 6-question answer-first FAQ, contact/CTA band, network footer. |
| `en.html` | Full English mirror (LTR), same structure, guides and FAQ. |
| `404.html` | Branded not-found page (Arabic). |

Plus: `styles.css`, `favicon.svg` (black + lime PR mark), `sitemap.xml`
(hreflang-annotated), `robots.txt`, `llms.txt`.

## Content retrofit (Nov 6, 2026 — content-first model)

Retrofitted to the owner's Nov 6 content-first model (sites lead with useful
content for search engines and AI answers, with influUGC's services and real
work woven in), following the aistore guides pattern: a **Guides** section now
opens the page flow (after the proof strip, before Services), with three
substantive, answer-first guides as anchor-linked on-page blocks, in both
languages:

1. `#guide-events` — how to invite influencers to an event properly.
2. `#guide-seeding` — product seeding that actually gets posted.
3. `#guide-brief` — how to brief an influencer for a launch.

Each guide closes with a woven-in influUGC line + the standard central CTAs
(booking + WhatsApp, `utm_source=prinfluencer`). No invented statistics.
Section numbering shifted (Guides 01 → Services 02 → Why 03 → Process 04 →
FAQ 05); header nav and footer nav link the guides; `llms.txt` carries guide
summaries with UTM CTAs. Guide blocks are on-page anchors, so `sitemap.xml`
is unchanged.

## SEO / GEO

- Canonical base `https://prinfluencer.net/` (the real domain — unlike
  ugccompany, which temporarily uses its onrender.com base; if this site is first
  deployed to an `onrender.com` URL before the domain attaches, switch all
  canonical/OG/sitemap/robots/llms bases in one pass, same as the ugccompany rule
  in `../DEPLOY.md` §2).
- Title/meta target "Influencer PR" + Egypt / Saudi Arabia in both languages;
  OpenGraph + Twitter cards; hreflang ar/en both ways.
- JSON-LD: `Organization` (with `parentOrganization: influUGC`, postal address,
  areaServed, the four real social profiles), `WebSite`, and `FAQPage` matching
  each page's visible FAQ word for word.

## CTAs (both carry the satellite UTM set)

- Booking → `https://www.influugc.com/book?utm_source=prinfluencer&utm_medium=satellite&utm_campaign=network`
- WhatsApp (client line) → `https://wa.me/201029979797?utm_source=prinfluencer&utm_medium=satellite&utm_campaign=network`
- Footer legal line: "Part of the influUGC network" linking to the hub.

## What remains (not done here)

1. **Deploy** — static folder; any static host or a Render Static Site (free tier
   per the network rule). No server/admin in this build: the brief scoped a static
   landing (ugccompany's own-admin pattern can be added later if wanted).
2. **Domain attach** — point `prinfluencer.net` DNS at the host (same checklist
   pattern as `../DEPLOY.md` §4: apex A + www CNAME from the host's screen; no MX
   changes — mail stays on influugc.com).
3. **influencer-pr-company.com 301** → prinfluencer.net (separate Phase-0 redirect
   step from the company-domains plan).
4. After go-live: dedicated Google Search Console property + submit
   `sitemap.xml`; verify both pages return 200 and the FAQ renders.

## Deploy status (Nov 6, 2026)

- **Repo**: https://github.com/mostafaabaas/prinfluencer (private, branch `main`) — source pushed Nov 6, 2026.
- **Hosting**: PENDING-DASHBOARD — the Render Static Site service has **not** been created yet.
  Creating it requires the Render dashboard (no Render API key is available to the
  automation): Render Dashboard → New → Static Site → connect this repo — the repo's
  `render.yaml` blueprint pre-fills the service name (`prinfluencer`) and publish path (`.`).
  Expected live URL once created: https://prinfluencer.onrender.com
- **Domain attach**: separate later batch (see "What remains" item 2 above).

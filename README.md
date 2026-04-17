# MoveZilla — Blog Page Explorations

Four blog page directions that extend the existing MoveZilla brand system. Open `index.html` to browse all four, or jump straight to a version below.

## How to preview

```
cd blog-designs
python3 -m http.server 8080
# → http://localhost:8080/
```

(Or open any `.html` in a browser directly — everything is static.)

## Design system reuse

Each page imports the same `shared/tokens.css`, which mirrors the live site's tokens and component classes **verbatim** from `/_astro/Layout.BJUd6zly.css`:

| Token | Value |
| --- | --- |
| `--color-brand-orange` | `#f97316` |
| `--color-brand-orange-light` | `#fb923c` |
| `--color-brand-green` | `#5caa36` |
| `--color-brand-green-dark` | `#124429` |
| `--color-ink` | `#0a0a0a` |
| `--color-ink-soft` | `#222` |
| `--color-surface-soft` | `#f8f8f8` |
| `--color-border-soft` | `#e7e7e7` |
| `--color-copy-muted` | `#565b72` |
| `--font-sans` | `Montserrat` (400–900) |
| Radii | sm 0.375 → 3xl 1.5rem (matches live) |
| Shadows | `--shadow-soft`, `--shadow-elevated` (verbatim) |

Shared components used across all four versions: `.page-shell`, `.section-padding`, `.kicker`, `.cta-primary`, `.cta-secondary`, `.icon-chip`, `.mz-header`, `.mz-footer`, `.mz-card`, `.mz-tag`, `.mz-read-more`, `.label-overline`.

---

## Version 01 — The Moving Journal (Editorial Magazine)

**File:** `v1-editorial-magazine.html`

**Design idea.** A branded "Moving Journal" shipped as Vol. 07. A cover-story hero dominates the top (image left, dek + byline right), followed by an issue rail ("In this issue: 01 → 06"), category "desks" with oversized numerals, a feature grid with one lead article, an editor's letter with pull quote, and a dark gradient newsletter module.

**Why it's different.** This is the only version built around *authorship and personality*. Issue numbers, bylines, editor's letter, Georgia italic pull-quote treatment — it reframes the blog as an editorial product rather than a content dump.

**Why it's still MoveZilla.** Every chrome piece — orange `.kicker` pills, gradient CTA, shadowed white cards, `.mz-footer` with ProMover badges, phone number in the header — is unchanged from the live site. The typographic scale and color use match the homepage exactly.

**On-brand CTA.** Newsletter capture styled as the homepage's dark "ink" section, plus persistent "Get Free Estimate" in the header.

---

## Version 02 — Resources (Minimal Authority)

**File:** `v2-minimal-authority.html`

**Design idea.** Calm, text-forward, library-like. Large typographic hero with a four-metric stat row (142 guides · 2,028 moves · 4.9/5 · 0% hidden fees). A sticky toolbar with search + category pills, three "Editor's Picks" as restrained bordered cards, then a long two-column index row (date, headline, dek, tag, read-time, arrow) that rewards skimming. Closes with a tonal inverted `ink`-colored CTA panel.

**Why it's different.** This version removes imagery from the article list entirely. No thumbnails, no photography in the grid — just typographic hierarchy and tabular dates. Density, rhythm, and whitespace carry the page.

**Why it's still MoveZilla.** Identical header, footer, kicker, and CTA styles. The stat row mirrors the homepage's "2,028 Successful Moves" pattern. The closing panel reuses the homepage's inverted dark gradient treatment.

**On-brand CTA.** Dark `.v2-cta-panel` at end of the list — "Most answers turn into an in-home estimate" — with primary orange CTA + secondary phone link.

---

## Version 03 — Moving Guides (Conversion Sidebar)

**File:** `v3-conversion-sidebar.html`

**Design idea.** Two-column layout engineered to convert readers into leads. Left column: breadcrumbs → topic filter bar → 2-col card grid → lead card → mid-grid CTA banner → pagination. Right column (sticky): mini estimate form, dark trust-score module, popular-articles rail, service-area tiles. Below 1024px the sidebar collapses and a fixed mobile quick-bar pins "Call · Estimate" to the bottom of the viewport.

**Why it's different.** Only version with a sticky lead-capture form, service-area cross-links, and a dedicated mobile sticky CTA. The layout is explicitly optimized for a blog reader who's mid-move-planning and ready to book.

**Why it's still MoveZilla.** The estimate form reuses the exact field grammar of the live site (Full Name / Phone / Move Date / From Where) and the same uppercase-tracking labels + orange focus ring. The trust module uses the homepage's 4.9/5 score treatment and testimonial copy.

**On-brand CTA.** Two redundant CTAs — the sticky estimate form (the site's signature lead-capture) and a mid-list "Book Free Estimate" banner styled in the homepage's dark-with-orange-glow pattern.

---

## Version 04 — The Playbook (Visual Resource Hub)

**File:** `v4-visual-resource-hub.html`

**Design idea.** An asymmetric "bento" hero with a large photo tile + an orange download tile + a green case-study tile + a soft playbook tile + a wide video tile. Below: six iconographic topic tiles, a dual-column checklist-preview + dark quote-stat module, a 4-up photo-led "Field Stories" strip, and a large dark closing CTA with radial orange glow.

**Why it's different.** This is the most image-led and playful direction. The bento shapes, downloadable checklist mockup with checked-off items, and field-story photo cards give the page a product-hub feel that the other three don't have.

**Why it's still MoveZilla.** Every color is `brand-orange`, `brand-green-dark`, or `ink`. The icon chips, kicker pills, and closer CTA use the site's gradient language. The photo overlays match the homepage's hero treatment (dark 100% gradient fade).

**On-brand CTA.** Closing CTA section with large orange gradient button + outlined phone button, framed by the site's signature radial orange glow on black.

---

## Content direction

All placeholder articles are on-brand for a moving company:
- "What flat-binding really means — and the four charges you should never see on an invoice" *(Pricing)*
- "The 6-week home seller's checklist" *(Selling)*
- "How to pack a kitchen in under a day without breaking a single plate" *(Packing)*
- "DMV to Chicago: a route playbook for the 750-mile relocation" *(Long Distance)*
- "The 'gap week': what to do when closings don't line up" *(Storage)*
- "Closing day logistics for sellers: the last 12 hours" *(Closing)*

Author voices are grounded in MoveZilla's co-founder narrative from the live site (Srdan Marjanović-Raić) plus realistic crew names. Stats match the homepage: 4.9/5, 120+ reviews, 2,028+ moves, FMCSA + ProMover certifications.

## Accessibility & responsiveness

- All interactive elements have `:focus-visible` outlines in brand orange.
- Semantic HTML: `<header>`, `<nav aria-label>`, `<main>` equivalents, `<section>`, `<article>`, `<aside>`, `<footer>`.
- All layouts collapse gracefully at `900px` and `640px` breakpoints.
- Images use `onerror` handlers so layouts degrade cleanly if a CDN image is blocked.
- Color contrast on ink-soft + brand-orange meets WCAG AA on white and on `#0a0a0a`.

## Where to deploy

The live MoveZilla site is built with Astro. To integrate any of these into that repo, each HTML file maps cleanly to a single Astro page (`src/pages/blog/*.astro`) — the class names, tokens, and components already match the site's existing Tailwind v4 setup (`bg-linear-to-r`, `brand-orange`, `section-padding`, `page-shell`, `cta-primary`, etc.). No new dependencies are required.

## Railway deploy

This folder is now wired to run as its own static Railway service.

### What was added

- `package.json` with a tiny static server (`serve`)
- `railway.json` so Railway starts it with `npm start`

Note: this uses plain static serving, not SPA fallback mode, so direct links like
`/v1-editorial-magazine.html` and `/v4-visual-resource-hub.html` resolve correctly.

### Local smoke test

```bash
cd blog-designs
npm install
npm run start:local
# -> http://localhost:3000/
```

### Railway steps

If you want this as a separate Railway service inside the existing repo:

1. Create a new service in Railway from this repository.
2. Set the service root directory to `blog-designs`.
3. Deploy.

Railway will detect `package.json`, install dependencies, and run:

```bash
npm start
```

If you prefer CLI later, the equivalent flow is:

```bash
cd blog-designs
railway init
railway up
```

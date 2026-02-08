# CLAUDE.md — Project Context for Claude Code

## What is this?
Single-page landing site for **Voxena** — an AI voice assistant for Belgian restaurants.
The site is a lead-gen page (no pricing displayed). Goal: get restaurant owners to fill the demo request form.

## Tech
- Single `index.html` file (~4000 lines, ~210KB)
- No framework, no build step, no npm — pure HTML/CSS/JS
- Google Fonts loaded via CDN
- Deploy target: Netlify static hosting at voxena.pro

## Architecture of index.html
The file has 3 blocks inside `<head>`:
1. **Meta tags** (SEO, OG)
2. **Single `<style>` block** (~2500 lines of CSS, including all 7 sections)
3. A second `<style>` block exists inside the footer's inline SVG logo — this is intentional, don't remove it

The `<body>` contains:
1. **Nav** (fixed, with dark-mode detection for the Problem section)
2. **Hero section** (light background)
3. **Problem section** (dark background, navy-deep)
4. **Bridge div** (gradient transition dark→light, 200px desktop / 80px mobile)
5. **Calculator section** (interactive sliders)
6. **Solution section** (3 scenario cards with chat transcripts)
7. **Platform section** (bento grid)
8. **Form section** (HubSpot lead capture)
9. **FAQ section** (accordion)
10. **Footer** (dark, with real Voxena SVG logo)

Scripts are at the bottom of `<body>`, one `<script>` block per section.

## Brand Colors
```
--blue: #74a3ff
--violet: #4237C4
--violet-dark: #3e3183
--navy: #0E1333
--navy-deep: #080B1F
--green: #1a9a5a
--green-soft: #34d399
--bg: #FAFBFE (light sections)
--white: #FFFFFF
```

## Known Issues to Fix
1. **Horizontal scroll on mobile** — something overflows viewport width. Check elements with negative positioning (hero orbs, floating badges) and fixed widths
2. **Bridge too tall on mobile** — already partially fixed with media queries but may need more reduction
3. **Navbar CTA button cut off on mobile** — the "Essai gratuit" button gets clipped on small screens
4. **Solution section title** — "La même soirée, avec VOXENA" — the word VOXENA may not be visible if the `.highlight` class green gradient isn't rendering
5. **Multiple IntersectionObserver instances** — each section creates its own, should be consolidated into one
6. **HubSpot IDs** — `YOUR_PORTAL_ID` and `YOUR_FORM_GUID` need real values
7. **Footer social links** — all point to `#`, need real URLs
8. **No favicon**

## Polish Wishlist
- Odometer-style counter animations (not linear increment)
- Sequential chat bubble reveals in solution scenario cards
- Calculator threshold effects (flash/highlight when loss exceeds 20K€)
- Smoother nav dark-mode transitions when scrolling through Problem section
- Micro-interactions on hover states
- Performance: consider splitting critical CSS

## Testing
Just open `index.html` in a browser. No server needed.
For mobile testing, use Chrome DevTools device emulation or deploy to Netlify preview.

# VOXENA — Landing Page

Site vitrine et page de capture de leads pour **Voxena**, l'assistant vocal IA pour restaurants belges.

## Stack

- **Pure HTML/CSS/JS** — aucun framework, aucun build step
- **Google Fonts** : Plus Jakarta Sans, Montserrat, JetBrains Mono
- **Déploiement** : Netlify (static hosting)

## Structure

```
voxena-website/
├── index.html      ← Landing page complète (7 sections)
├── assets/
│   └── logo.svg    ← Logo Voxena (SVG vectoriel)
└── README.md
```

## Sections

| # | Section | Theme | Anchor |
|---|---------|-------|--------|
| 1 | Hero | Light — value prop + phone mockup | — |
| 2 | Problem | Dark — timeline d'appels manqués | — |
| 3 | Calculator | Light — estimateur interactif de coûts | `#calculator` |
| 4 | Solution | Light/green — 3 scénarios avec transcripts chat | `#features` |
| 5 | Platform | Light — bento grid des fonctionnalités | — |
| 6 | Form | Light — formulaire de capture HubSpot | `#contact` |
| 7 | FAQ + Footer | Light→Dark — accordion FAQ + footer branded | `#faq` |

## Brand

- **Violet** : `#4237C4` (primary CTA)
- **Blue** : `#74a3ff` (accents)
- **Navy** : `#0E1333` (dark sections)
- **Green** : `#1a9a5a` (success/solution)
- **Fonts** : Carla Sans (headings) / Montserrat (body)

## TODO — Polish final

- [ ] Remplacer `YOUR_PORTAL_ID` et `YOUR_FORM_GUID` par les vrais IDs HubSpot
- [ ] Remplacer les liens sociaux `#` dans le footer par les vrais URLs
- [ ] Fix responsive mobile (scroll horizontal, bridge trop haut, navbar CTA coupée)
- [ ] Ajouter animations odometer sur les compteurs
- [ ] Ajouter reveal séquentiel des bulles chat dans les scénarios
- [ ] Consolider les IntersectionObserver (actuellement dupliqués par section)
- [ ] Optimiser performance (critical CSS inline, lazy-load)
- [ ] Ajouter favicon
- [ ] Tester cross-browser (Safari, Firefox, Chrome mobile)

## Déploiement Netlify

1. Connecter ce repo à Netlify
2. Build command : *(vide — pas de build)*
3. Publish directory : `.` (racine)
4. Brancher le domaine `voxena.pro`

# Assembly Industries — site

Multi-page marketing site for **assembly-industries.com**. Astro + Tailwind v4 (CSS-first tokens), scoped Astro `<style>` blocks, no shipped JS except a single use-case tab toggler on `/delivery`.

## Pages

| Path | Component | Purpose |
|---|---|---|
| `/` | `src/pages/index.astro` | Home — AI enablement wedge, two-doors framing, proof, CTA |
| `/platform` | `src/pages/platform.astro` | The "build it yourself" door · governed builder UX deep dive |
| `/delivery` | `src/pages/delivery.astro` | The "we build it" door · Studio engagement + three-person team + capabilities |
| `/pricing` | `src/pages/pricing.astro` | Two tracks, both usage-based |

## Develop

```sh
npm install
npm run dev      # http://localhost:4321
npm run build    # → dist/
```

## Deploy

```sh
netlify deploy --prod
```

## Structure

```
src/
├── layouts/Layout.astro            shared shell — title, meta, fonts, nav, footer
├── components/
│   ├── Nav.astro
│   ├── Footer.astro
│   ├── BuilderArtifact.astro       hero artifact · live-builder UI mock
│   ├── Hero.astro                  homepage hero
│   ├── Problem.astro               Shadow AI · nowhere to build · pressure
│   ├── HowItWorks.astro            3-stage flow
│   ├── TwoDoors.astro              platform + delivery cards
│   ├── Speed.astro                 before/after event log
│   ├── Included.astro              5-group capability teasers
│   ├── Proof.astro                 3 case-study spines
│   ├── ClosingCTA.astro
│   ├── delivery/                   /delivery sections
│   └── platform/                   /platform sections
├── pages/
│   ├── index.astro
│   ├── platform.astro
│   ├── delivery.astro
│   └── pricing.astro
└── styles/global.css               design tokens (@theme) + primitives

docs/visual-references.md           Phase-2 research · steal-list and anti-patterns
```

## Design tokens

All in `src/styles/global.css` as Tailwind v4 `@theme` variables.

- **Color**: indigo (50/100/500/600/700) + lavender + ink (50–950) + sage/amber (product chrome only)
- **Type**: Space Grotesk (display) · Inter (body) · JetBrains Mono (eyebrows · IDs · code)
- **Radii / shadow**: `--radius-sm/md/lg/xl`, `--shadow-card/hover`

## Outstanding before launch

- Real customer names + outcomes for the homepage Proof section + the platform "Built on Assembly" cards
- Real scheduling link wired into "Book a scoping call" CTAs (Cal.com / Calendly / HubSpot)
- Confirm `founders@assembly-industries.com` is a real / routed inbox
- Finalize pricing numbers (`/pricing` currently uses working illustrative ranges)
- Add OG image + favicon
- Wire continuous deploy (GitHub → Netlify) — current setup is manual `netlify deploy --prod`

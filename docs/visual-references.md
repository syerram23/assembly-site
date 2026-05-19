# Visual references — Assembly Industries landing page

## 1. Sites worth studying

- **Linear** — https://linear.app — Pioneered the "calm warm-gray" dark mode and the layered, animated hero where product surfaces (issue rows, command bar, status pickers) dock and slide as you scroll. Inspires: **Hero (builder UI artifact), Platform builder UI page**. The most-copied hero on the web for a reason: every visible element looks like a live screenshot because individual components are real DOM, not flattened PNGs.

- **Vercel** — https://vercel.com — "Deploy. Preview. Ship." hero pairs a confident black canvas + Geist type with a real preview-deployment surface (commit SHA, deploy state) animating in. Inspires: **Hero, Speed graphic** (their flow visual treats CI/CD as a series of timestamped events — directly transferable to our Sources→Logic→Surface).

- **Stripe** — https://stripe.com — Sohne at 300 weight with negative tracking, indigo + atmospheric gradient mesh, composited product mocks beside every feature. Inspires: **Hero, Platform builder page, Pricing**. Tabular figures everywhere money/IDs appear.

- **Stripe Press** — https://press.stripe.com — Benchmark for "premium services firm with taste." 3D book objects, generous editorial grid, serif drop. Inspires: **Proof/Case-studies as named artifacts**, the *Quarterly*-style insights section if we have one.

- **Palantir** — https://www.palantir.com — Heads-Up-Display navigation, quadrant layout, mil/intel-grade restraint. Sector pages (Defense, Health, Energy) are essentially industrial case studies. Inspires: **Two-doors framing, Delivery process page**.

- **Mercury** — https://mercury.com — Dark cinematic palette, Arcadia custom face, desaturated chrome instead of fintech-blue, levitating product objects with subtle shimmer. Inspires: **Hero artifact treatment** (how to make a UI feel like a *physical* object).

- **Plaid** — https://plaid.com — Best-in-class "data flowing between systems" visuals using patterned fills + directed-graph thinking. Inspires: **Speed graphic, Platform builder UI page** (Sources→Logic→Surface is a directed graph).

- **Anthropic** — https://www.anthropic.com — Modular content blocks, "Latest releases" as dated/categorized cards, narrative case studies that read editorial, not promotional. Inspires: **Proof/Case-studies, Delivery process page**.

- **BCG X** — https://www.bcg.com/x — Hybrid build-and-design positioning communicated through a modular component system. Inspires: **Two-doors framing**.

- **McKinsey Quarterly** — https://www.mckinsey.com/quarterly — Custom Bower typeface, McKinsey-deep-blue on white, immersive long-form. Inspires: **Proof/Case-studies treated as essays, not cards**.

## 2. Patterns to steal

1. **Linear-style "real components" hero, not a screenshot.** Sources/Logic/Surface columns as actual HTML/CSS — real rows, real monospace IDs, real status pills that animate state changes on a loop. The eye reads "DOM" vs "PNG" instantly.
2. **Vercel-style timestamped event log as the Speed graphic.** Render the four-week build as a CI-style stack of dated events (`brief → wired prototype → pilot → cutover`) with commit-sha-like IDs. Reads as engineering.
3. **Stripe Press-style case studies as named artifacts.** Each case study gets a "spine" — a hero object (the actual internal tool: `hr-comp-band-bot`, `claims-triage-v2`) shown 3D-ish with metadata (vertical, stack, time-to-cutover, $ delta). Beats logo walls.
4. **Plaid-style directed-graph flow visual** for the Platform builder UI page: Sources left, Logic middle, Surface right. Lines = actual edges with labels (`OAuth`, `webhook`, `REST`).

## 3. Anti-patterns to avoid

1. **Stock "AI" chrome** — gradient orbs, neural-net swirls, glowing brains, isometric robot hands. Every undifferentiated AI services site uses these.
2. **Floating laptop/phone screenshots tilted at 15°** with drop shadows (Big-4 consulting deck staple). Show product UI flat, sharp, full-bleed — Linear/Vercel approach — never as a hero device photo.
3. **Logo-wall-as-proof** without context. Pair every logo with a one-line outcome (cohort, system, measurable result).

## 4. The hero artifact — opinionated build spec

Build it as **three real DOM columns inside a single windowed surface**, not three floating screenshots. The window has a single faux-chrome title bar reading `assembly · builder · hr-comp-band-bot` in JetBrains Mono — that one detail makes the whole thing read as a real app shell rather than a marketing mock.

Each column is a stack of typed component rows:
- **Sources**: `workday.employees`, `greenhouse.offers` with live-looking sync indicators (small pulsing dots, last-synced timestamps in mono)
- **Logic**: two stacked nodes — a `level_band_lookup` transform and a `pii_redact` policy — with input/output type chips (`Employee → BandRange`)
- **Surface**: three endpoint pills (`slack`, `web`, `rest`) each with a tiny example payload preview

The animation loop should be **state changes, not motion** — a sync dot ticks, a row highlights as data flows left-to-right along a hairline rule, a Slack preview at the bottom-right updates its reply.

Specifically borrow from Mercury: make the window feel like a *physical object* — sub-pixel inner border, faint chromatic edge, no drop shadow but a slight gradient on the chrome bar.

Avoid: tilting the surface, mocking with Lorem ipsum, abstract particle effects, more than ~9 rows total across the three columns. Restraint is what separates "real product" from "product mock."

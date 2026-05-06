# Mamba ArchViz — Design System

> Architectural visualization, 360° tours and immersive content design for **Carlos Díaz** (Barcelona, ES).
> This design system supports the migration from Squarespace → custom GitHub Pages site, plus the new **Backwalls** product landing.

---

## 1. Studio context

**Mamba ArchViz** is the practice of **Carlos Díaz**, a Barcelona-based architect specialising in architectural visualization. Three product lines:

| Surface | What it is | Audience |
|---|---|---|
| **Portfolio site** (mambaarchviz.com) | Main landing — hero, renders gallery, 360° tours, films, about, contact | Studios, developers, hospitality clients |
| **Backwalls** (sub-landing) | New product line: bespoke architectural backdrops for content creators / streamers | Independent creators, video producers |
| **Direct contact** | Email + form (`mambaarchviz@gmail.com`) | All clients |

The voice is **facts-first, engineering-minded, artisanal**. Bilingual: **Spanish (primary) + English (secondary)**. Always with a language selector.

### Where this came from

| Source | Path | Read-only? |
|---|---|---|
| Briefing (Spanish, full client requirements) | `mambaarchviz/web-files/BRIEFING-OPUS.md` | yes |
| Existing Squarespace screenshots (21) | `mambaarchviz/web-reference/*.PNG` | yes |
| Logo set | `mambaarchviz/web-reference/Logos/` | yes |
| Background plates | `mambaarchviz/web-reference/backgrounds currents/` | yes |
| Render archive (110+ images) | `mambaarchviz/renders/` | yes |
| Old prototype (control panel for theme exploration) | `mambaarchviz/web-files/prototipo-interactivo.html` | yes |
| **Visual style reference (new direction)** | https://godly.website/website/cosmos-978 → https://www.cosmos.so/ | external |

The **Cosmos.so direction** is the key shift: dark, editorial, large serif display headlines, image-led storytelling, generous negative space. The old Squarespace site is light, sparse, with thin geometric headers and coral CTAs — we keep its architectural quietness and the MAMBA wordmark/triangle DNA, but warm the page with serif display + dark theme.

---

## 2. Index

| File / folder | What's in it |
|---|---|
| `README.md` | This file. Start here. |
| `colors_and_type.css` | All design tokens — color, type, spacing, motion, semantic helpers (`h1`, `.brand-eyebrow`, etc). Drop into any artifact. |
| `assets/` | Logos, icons, render samples, background plates. Copy-out, don't rebuild. |
| `assets/logos/` | MAMBA wordmark (5 variants) + circle/triangle marks + animation frames |
| `assets/services/` | Service icons (renders, 360, films, 2D — heritage triangle motif) |
| `assets/renders/` | Curated 12-image render archive (residential, interiors, exteriors, hospitality) |
| `assets/backgrounds/` | Concrete + signature triangle pattern plates |
| `index.html` | Main portfolio site — hero, gallery, 360 tours, films, Backwalls teaser, about, contact |
| `ui_kits/portfolio/` | Componentized version of the main site (JSX) |
| `ui_kits/backwalls/` | Dedicated Backwalls landing page — coral accent, product-focused |
| `preview/` | Design-tab cards (type, color, components, brand) |
| `SKILL.md` | Agent skill manifest — read first if you're picking this up as a skill |

---

## 3. Content fundamentals

### Voice

**Spanish-first, English-second.** The Spanish copy is **familiar but precise** ("Colaboramos contigo para crear las imágenes más representativas de tu proyecto"). It uses **"tú"**, never "usted" — direct, peer-to-peer with creative clients.

The English version is matter-of-fact and lightly editorial — never marketing-bro.

| Trait | Yes | No |
|---|---|---|
| Tone | Calm, confident, technical | Hype, exclamation, urgency |
| Person | "we" / "nosotros" — the studio | "our team is passionate about…" |
| You-ness | Direct ("tu proyecto", "your project") | Corporate ("our valued clients") |
| Casing | Sentence case in body. **UPPERCASE** for nav, eyebrows, button labels (heritage Squarespace move kept). Headlines mix sentence case + an italic editorial fragment. | Title Case Everywhere |
| Emoji | **Never.** No emoji anywhere. | 🎨🏛️✨ |
| Punctuation | Periods. Em-dashes for pauses. **Italic** to set off the poetic fragment ("made *visible*", "una *hipótesis* de futuro"). | Exclamation marks, all-caps for emphasis |

### Headline pattern (signature move)

The Cosmos.so-derived headline structure pairs a sober statement with one italic fragment:

> *"Architecture, **made visible.**"*
> *"Cada proyecto, **una hipótesis de futuro.**"*
> *"Camina por el proyecto **antes de levantarlo.**"*
> *"Cuando la imagen **no es suficiente.**"*

Always use this pattern for section H2s. The italic part is in **Instrument Serif italic** and carries the feeling; the roman part anchors it.

### Eyebrows / labels

Every section opens with a **mono-uppercase eyebrow** in JetBrains Mono, gold or muted, with a 24px hairline rule on its left:

```
─── 360° VIRTUAL TOURS
─── SELECTED WORK · 2018 — 2026
─── STUDIO
```

This is the architectural-spec signal: technical, archival, "facts-first".

### Project metadata

Every render / project gets a **classification code** (e.g. `001 / RES`, `004 / HOSP`, `006 / WELL`) shown in mono. This echoes architectural archive numbering and is the only place numbers/stats are used (avoid stat-slop elsewhere).

### Sample copy library

| Where | ES | EN |
|---|---|---|
| Hero | Architecture, *made visible.* | Architecture, *made visible.* |
| Hero sub | Visualización arquitectónica de alta gama, recorridos 360° y contenido inmersivo para estudios, promotores y creadores. | High-end architectural visualization, 360° tours and immersive content for studios, developers and creators. |
| Portfolio | Cada proyecto, *una hipótesis de futuro.* | Each project, *a hypothesis for the future.* |
| 360 Tours | Camina por el proyecto *antes de levantarlo.* | Walk through the project *before it's built.* |
| Films | Cuando la imagen *no es suficiente.* | When a still image *isn't enough.* |
| Backwalls | Backwalls. *Tu fondo, hecho a medida.* | Backwalls. *Your backdrop, on demand.* |
| Contact | ¿Tienes un proyecto *en mente?* | Have a project *in mind?* |

---

## 4. Visual foundations

### Color

The system is **dark-first** (dark theme is canonical; the legacy white-on-white look is reserved for the splash/language selector only).

**Surface ramp** — `--bg-0` `#0a0a0a` (deepest / footer / hero overlay) → `--bg-1` `#111111` (canvas) → `--bg-2` `#161616` (cards) → `--bg-3` `#1d1d1d` (hover). All neutrals are slightly **warm-leaning** (no blue tint) — this matches the warmth of architectural renders.

**Foreground** — `--fg-0` `#ffffff` (display) → `--fg-1` `#f2efea` (body, warm off-white) → `--fg-2` `#b8b3aa` (secondary) → `--fg-3` `#6e6a63` (captions). Foreground neutrals carry a subtle **paper warmth** that prevents the dark UI from feeling clinical.

**Two accents — used at different fidelity:**
- **Gold** `#d4af37` — primary on dark theme. CTAs, active links, eyebrows, hover. The "premium architectural" signal.
- **Coral** `#ff6b6b` — heritage accent kept from the Squarespace site. **Reserved for Backwalls product surface and error states.** Coral marks "creator/community/playful" as opposed to gold's "studio/premium".

**Render-tone palette** (use as supporting tints only, never flat fills):
`--tone-concrete` `#b9b1a4` · `--tone-timber` `#8a6a4a` · `--tone-moss` `#5a6a4f` · `--tone-sky` `#c8d3dc`

### Type

Two-family pairing:

- **Instrument Serif** — display headlines, italic editorial moments. High-contrast modern serif (free, Google Fonts; closest to GT Super Display from the Cosmos.so reference, **without** the "Fraunces problem" — see Caveats).
- **Jost** — UI, body, nav, buttons, eyebrows. Geometric grotesk that echoes the thin MAMBA wordmark.
- **JetBrains Mono** — captions, project codes, eyebrows, technical specs.

Scale is modular (1.250 ratio, fluid via `clamp()`). See `colors_and_type.css` for the full ramp.

**Tracking** is the architectural signature: nav and eyebrows use `--tracking-widest` (0.32em), body is normal, headlines are slightly tight (`-0.02em`).

### Spacing

8-step scale: `4 · 8 · 12 · 16 · 24 · 32 · 48 · 64 · 96 · 128 · 192 px`. The high end (`--s-11` 192px) is **load-bearing** — generous whitespace is the brand. Sections breathe at 96–160px vertical padding.

### Backgrounds

- **Pure dark canvas** is the default — no gradients on body.
- **Hero backgrounds**: a render image at ~18% opacity behind a radial mask, sitting on `--bg-0` → `--bg-1`. Architectural imagery becomes atmosphere, not decoration.
- **Section transitions**: subtle `linear-gradient` between `--bg-1` and `--bg-0` to create depth without visible seams.
- **No emoji backgrounds, no big gradients, no blob shapes.** The triangle pattern from the legacy site is preserved as `assets/backgrounds/bg-pattern-dark.jpg` for selective use.
- **Grain overlay**: a 4%-opacity SVG noise via `mix-blend-mode: overlay` on `body::before`. Adds the analog feeling that distinguishes editorial dark themes from generic SaaS dark mode.

### Imagery

The render archive is **already warm-toned** (timber, concrete, dusk). When tiling thumbnails:
- Apply `filter: grayscale(0.15) brightness(0.92)` at rest.
- Restore to full color + slight zoom (`scale(1.04)`) on hover.
- This produces the "comes alive on hover" effect the briefing requires, with cohesion across mixed renders.

The hero image gets a stronger desaturation (`grayscale(0.4)`) and is **masked behind a radial gradient** so the headline reads cleanly.

### Animation

- Easings: `--ease-out` for nav/buttons, `--ease-arch` (`cubic-bezier(0.16, 1, 0.3, 1)`) for image reveals — slow-out, very architectural.
- Durations: `180ms` (UI), `400ms` (transitions), `800ms` (image hovers), `1200ms` (parallax reveal — the heritage "destapado" effect).
- **No bounces, no springs.** The brand is rectilinear and quiet.
- Scroll-reveal: opacity 0→1 + translateY 24px→0 over 1s with `--ease-arch`.
- The hero scroll cue pulses a 1px vertical line.

### Hover & press states

| Surface | Hover | Press |
|---|---|---|
| Nav link | color → `--fg-0` (sometimes gold) | — |
| Nav CTA (ghost) | border → gold, text → gold | — |
| Primary button (gold) | bg → `--gold-soft`, `translateY(-1px)` | — |
| Coral button | bg → `--coral-soft` | — |
| Ghost button | border → `--fg-0`, bg → 5% white | — |
| Image tile | scale 1.04, grayscale 0, overlay fades in | — |
| Video play button | bg fills gold, icon turns black | — |

**Borders** are hairlines: `rgba(255,255,255,0.08)` for dividers, `0.16` for visible borders, `0.32` for emphasis. Architectural drafting lines, not card chrome.

### Shadows

Almost invisible. Most surfaces use a hairline border instead of elevation. When shadow is needed:
- `--shadow-1`: subtle, keyboard-popped.
- `--shadow-2`: card depth (rarely used).
- `--shadow-glow`: gold ring + glow — reserved for highlighted CTAs only.

### Corner radii

**Restrained.** Default `--radius-1` is **2px**, image tiles are 4px, only chips and play buttons use `999px`. Never pill buttons. Never blob shapes. The brand is rectilinear — straight lines, sharp corners, drafting marks.

### Cards

A "card" in this system is just an **image tile + hairline border + tiny mono index code**. No drop shadow, no rounded corners > 4px, no left-border accent line. The image *is* the card; everything else gets out of the way.

### Layout rules

- Max content width: **1400px**, centered.
- Page-level horizontal padding: 40px desktop / 20px mobile.
- Gallery: 12-column grid with **asymmetric tile sizing** (large/tall/wide/third) — not a uniform 4-up. This is the editorial move: rhythm, not regularity.
- Navigation is **sticky + blurred** with a 14–22px height shrink on scroll.
- Section vertical rhythm: 96–160px.

### Transparency & blur

- Nav uses `backdrop-filter: blur(18px)` on a top-fading dark gradient.
- Tile-meta chips and image tags use `rgba(0,0,0,0.6)` + `blur(8px)`.
- Reserved for floating UI only — never on body content.

---

## 5. Iconography

The brand has **no built-in icon font**. Iconography happens at three layers:

1. **The MAMBA wordmark itself** — it's geometric (M = stacked triangles, A = triangle, B = circles). All headers ship the wordmark, not a separate icon. It scales from 22px (nav) to massive hero size.
2. **The triangle pattern** — repeating tessellated triangles with tiny "BA" letterforms inside, from the legacy site. Stored at `assets/backgrounds/bg-pattern-dark.jpg` and `bg-pattern-light.jpg`. Use sparingly as a section break or signature flourish.
3. **The "MBA" circular mark** — round badge with the wordmark on a dotted geometric grid. Available in light (`logo-circle-light.png`) and dark (`logo-circle-dark.jpg`) variants. Use as a favicon, social avatar, or tiny watermark on individual renders.

**Service icons** (`assets/services/icon-renders.jpg`, `icon-360.jpg`, `icon-movie.jpg`, `icon-2d.jpg`) — heritage round badges with abstract architectural illustrations inside the triangle grid. They're **photographic JPGs**, not vector — keep using them as raster tiles, don't try to redraw.

**Logo animation frames** (`assets/logos/anim-frame-*.png`) — 5 keyframes from the existing site's parallax "wordmark reveal" effect. Available if implementing the heritage scroll-reveal on the new site.

**UI iconography (arrows, play, close)** — drawn inline as **simple SVG** (3 polygon points, no embellishment). Examples in `index.html`: the play triangle is `M3 1l11 7-11 7z`, the arrow is the unicode "→" character. **Do not import an icon library** — the brand voice has so few icons that any library would feel incongruous.

**Emoji**: never.

**Unicode glyphs allowed**: `→` `·` `—` `/` only.

---

## 6. Caveats & flags

1. **Font substitution**: The Cosmos.so reference uses **GT Super Display** (commercial). I substituted **Instrument Serif** (Google Fonts, free) — same high-contrast, refined-modern serif feel, slightly less editorial weight. **Flag for client**: confirm whether to license GT Super or stay on Instrument Serif.
2. **Type font for body**: **Jost** (Google Fonts) — geometric grotesk in the spirit of the existing Squarespace site's "Trebuchet MS / Geometric Modern" choice from the prototype. If client has a corporate font, substitute.
3. **Render image rights**: The 12 sample renders in `assets/renders/` are from `mambaarchviz/renders/` — confirmed Mamba's own work per the briefing.
4. **Color decision**: The briefing left "gold OR coral" open. This system uses **gold = primary, coral = Backwalls/secondary** to preserve both heritage and the new premium feel. Single-accent variants are easy via Tweaks.
5. **No CMS / no language switching backend**: The bilingual selector is visual-only in this kit. Real implementation will need static i18n or two pages.

---

## 7. Project index — what's where

```
mamba-archviz/
├── README.md                       This file.
├── SKILL.md                        Agent skill manifest — start here if invoked as a skill.
├── colors_and_type.css             All design tokens. Drop into any artifact.
├── index.html                      MAIN SITE — portfolio, hero → contact, full nav.
├── assets/
│   ├── logos/                      5 wordmark variants + circle marks + 5 anim frames
│   ├── renders/                    12 curated renders (residential / interior / hospitality)
│   ├── services/                   4 heritage round badges (renders / 360 / films / 2D)
│   └── backgrounds/                Concrete plate, triangle pattern (dark + light)
├── preview/
│   ├── type.html                   Specimen — Instrument Serif × Jost × JetBrains Mono
│   ├── colors.html                 Surfaces, fg ramp, gold + coral, render tones
│   ├── spacing.html                8-step scale, radii, shadow tiers
│   ├── components.html             Buttons, tiles, chips, nav, inputs
│   └── brand.html                  Wordmarks, circle marks, anim frames, pattern, service icons
└── ui_kits/
    └── backwalls/
        └── index.html              BACKWALLS — product sub-landing (coral accent)
```

Both `index.html` and `ui_kits/backwalls/index.html` are **production-shaped** — they're not throwaway examples. Use them as starting points for client deliverables.

## 8. Quick start for designers / agents

1. Drop `<link rel="stylesheet" href="colors_and_type.css">` into your HTML.
2. Use semantic classes: `.brand-display`, `.brand-h2 em`, `.brand-eyebrow`, `.brand-navlink`.
3. Pull assets from `assets/` — never re-draw the logo or icon set.
4. For headlines, follow the **roman + italic fragment** pattern.
5. For sections, lead with a `.section-eyebrow` (mono uppercase, hairline rule).
6. Default to dark theme. Light theme is splash-only.
7. Hover states: image tiles zoom + desaturate-off; CTAs lift 1px or shift color, never bounce.
8. See `ui_kits/portfolio/` and `ui_kits/backwalls/` for reference recreations.

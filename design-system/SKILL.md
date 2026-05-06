# Skill — Mamba ArchViz Design System

You are designing for **Mamba ArchViz**, a Barcelona-based architectural visualization studio led by **Carlos Díaz**. The system covers a portfolio site, a **Backwalls** product sub-landing, and any future client deliverables.

## Always do this first

1. **Read `README.md`** — full content, voice, color, type, spacing, motion, iconography rules.
2. **Read `colors_and_type.css`** — single source of truth for tokens. Link it in every artifact: `<link rel="stylesheet" href="colors_and_type.css">`.
3. **Browse `assets/`** before drawing anything: logos, render archive, backgrounds, service icons. Reuse, don't redraw.
4. **Reference `index.html`** (main site) and `ui_kits/backwalls/index.html` for layout patterns and the Cosmos.so editorial style — they are the canonical examples.
5. **Open the design tab** to scan `preview/type.html`, `preview/colors.html`, `preview/spacing.html`, `preview/components.html`, `preview/brand.html` for visual reference of every token.

## Surface map

| Surface | Path | Accent |
|---|---|---|
| Main portfolio | `index.html` | Gold `#d4af37` |
| Backwalls landing | `ui_kits/backwalls/index.html` | Coral `#ff6b6b` |
| Design tokens | `colors_and_type.css` | — |
| Preview cards | `preview/*.html` | — |

## Non-negotiable rules

- **Spanish primary, English secondary.** Use "tú", never "usted".
- **Headlines pair roman + italic fragment** — *"Architecture, made visible."* The italic carries the feeling.
- **Eyebrows mark every section** — JetBrains Mono uppercase + 24px hairline rule, gold or coral.
- **Dark theme is canonical.** Light theme is splash-only.
- **Gold = primary** on portfolio. **Coral = Backwalls + heritage + error** only.
- **Restrained radii** — max 4px on tiles, 2px on buttons. Never pill, never blob.
- **Hairline borders** carry depth — almost no shadows.
- **No emoji. No icon library.** SVG arrows + play triangle only.
- **Image tile interaction** — at rest `grayscale(0.15) brightness(0.92)`; on hover `scale(1.04)` + full color.
- **Font substitution flag** — Instrument Serif stands in for GT Super; Jost for the legacy geometric sans. Confirm with client before licensing.

## Common tasks

| Task | Pattern |
|---|---|
| New landing section | `<section class="section">` with `.section-eyebrow` + `.section-title em` + `.section-lead` |
| Add a render to gallery | Drop into `assets/renders/`, reference in `.gallery` with `t-large/t-tall/t-wide/t-third` sizing for asymmetric rhythm |
| Speak about Backwalls | Coral accent, creator-language, "creator/streamer/producción". Never gold. |
| Speak about portfolio | Gold accent, studio-language, "promotor/estudio/proyecto". |
| New CTA | `.btn-primary` (gold) for portfolio; `.btn-coral` for Backwalls; `.btn-ghost` for secondary |
| New page | Inherit from `index.html` head; copy nav structure; keep grain overlay + reveal-on-scroll |

## Caveats

See `README.md § 6` — fonts are open-source substitutes, render rights are confirmed Mamba's, bilingual switcher is visual-only.

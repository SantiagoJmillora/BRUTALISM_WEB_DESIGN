# Design system

> Tokens and rules. Source of truth in code: `src/styles/tokens.css` (exposed to Tailwind via `@theme`).
> Naming: kebab-case in code (`--color-ink`), `/` in Figma (`color/ink`). No loose hex/px values in components.

_Pending — to be filled during phase F2 after Santiago approves the options._

## Typography

Status: **A approved (2026-11-12): Barlow Condensed (display Black / heading Bold) + Barlow (text Regular / SemiBold) + IBM Plex Mono (data).** Figma: `01 Foundations` › "F2 · Typography (F2-01)". All fonts: Google Fonts, SIL OFL, self-hosted with `next/font/google`. Availability verified on fonts.googleapis.com and in Figma (2026-11-12).

| | A — Barlow Condensed + Barlow + IBM Plex Mono ★ | B — Anton + Inter + JetBrains Mono | C — Big Shoulders Display + Public Sans + Space Mono |
|---|---|---|---|
| Voice | Swiss-industrial superfamily (from highway signage: civic/infrastructure) | Poster punch, neutral UI text | Civic-industrial (Chicago signage + US gov system), quirky mono |
| Display / heading / text / mono | Cond Black · Cond Bold · Regular/SemiBold · Plex Mono Regular | Anton · Inter Bold · Inter Regular/SemiBold · JetBrains Mono | BSD Black · BSD ExtraBold · Public Sans Regular/SemiBold · Space Mono |
| UX | + Legible body; condensed display fits long names at 390 px | + Inter great for forms. − Anton single weight, very common | + Public Sans very legible. − Space Mono wide (spec rows wrap); BSD needs ≥ 40 px |
| Conversion | + Calm form copy, loud-but-disciplined display | + Loudest hero. − Template-like pairing | + Most distinctive. − Three voices to balance |
| Perf (woff2, approx.) | Static family → ~5 files ≈ 120–150 KB | ≈ 110 KB | ≈ 130 KB |

### Fluid scale (shared by all options; clamp between 390 and 1440 px)

| Token (Figma `font/size/…` · CSS `--font-size-…`) | 390 px | 1440 px | Role |
|---|---|---|---|
| display-xl | 150 | 360 | Hero word ("OPUS") |
| display-l | 54 | 128 | Headlines, project names in hero |
| heading-1 | 40 | 72 | Page titles |
| heading-2 | 28 | 48 | Section titles |
| heading-3 | 20 | 28 | Card titles |
| body-l | 18 | 20 | Intros |
| body | 16 | 18 | Body, form inputs (≥ 16 px avoids iOS zoom) |
| small | 14 | 15 | Secondary text |
| caption | 12 | 13 | Mono metadata, spec labels |

Formula: `clamp(min, min − slope·3.9px + slope·vw, max)` with `slope = (max − min) / 10.5` (vw). Example body: `clamp(1rem, 0.954rem + 0.19vw, 1.125rem)`.

Recommendation: **A**.

## Color

Status: **options proposed (F2-02), awaiting approval.** Figma: `01 Foundations` › "F2 · Color (F2-02)". Ratios computed with the WCAG 2.x relative-luminance formula.

Tokens (all options): `color/ink` · `paper` · `muted` (secondary text on paper) · `concrete` (secondary on ink, decorative borders, disabled) · `accent` · `on-accent` · `error` · `success` · `overlay` (ink at 65% over photos) · `focus` (3 px ring, 2 px offset; ink on light, paper on dark).

| Token | A — Concrete + Signal Orange ★ | B — Strict monochrome | C — Ink + Acid Green |
|---|---|---|---|
| ink | `#111111` | `#000000` | `#0B0F0C` |
| paper | `#F2F0EB` | `#FFFFFF` | `#EEF0EA` |
| muted | `#5C5A55` | `#595959` | `#545A55` |
| concrete | `#C9C6BF` | `#D9D9D9` | `#C5CAC3` |
| accent | `#FF5A1F` | `#000000` (= ink) | `#C8FF2E` |
| on-accent | `#111111` | `#FFFFFF` | `#0B0F0C` |
| error | `#B3001B` | `#C00000` | `#B3261E` |
| success | `#1E6B34` | `#1A7F37` | `#1E6B3A` |

| Pair | A | B | C |
|---|---|---|---|
| ink / paper | 16.6 ✓ | 21.0 ✓ | 16.8 ✓ |
| muted / paper | 6.1 ✓ | 7.0 ✓ | 6.2 ✓ |
| on-accent / accent (CTA text) | 6.1 ✓ | 21.0 ✓ | 16.4 ✓ |
| accent / ink (CTA on dark) | 6.1 ✓ | 1.0 ✗ (CTA inverts to paper) | 16.4 ✓ |
| accent / paper (CTA edge, needs 3:1) | 2.7 ✗ → 2 px ink border | 21.0 ✓ | 1.0 ✗ → ink border / ink surface |
| error / paper | 6.3 ✓ | 6.5 ✓ | 5.7 ✓ |
| success / paper | 5.8 ✓ | 5.1 ✓ | 5.7 ✓ |
| paper / overlay (ink 65% over pure white) | ≥ 4.5 ✓ | ≥ 4.5 ✓ | ≥ 4.5 ✓ |

Overlay: ink 55% is enough for display text (large, 3:1) but body text over photos needs ≥ 60–65% → token fixed at 65%.

Recommendation: **A** — the CTA is the only orange element on screen (maximum salience); rule: CTA on light surfaces gets a 2 px ink border; errors always icon + text (orange ≈ red family).

## Grid & spacing

_Pending (F2-03)._

## Motion

_Pending (F2-04). Include reduced-motion rules._

## Tokens

_Pending (F2-05)._

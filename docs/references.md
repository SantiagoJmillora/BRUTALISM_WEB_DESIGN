# References summary

> Single source of truth for the visual references (`Referencias ESTRUCTURALES` + `Referencias WEB`, 9 images).
> Written once (task F0-05). The reference images are **not** re-read after this file exists.

## Structural references (architectural mood)

| # | What it shows | What it contributes |
|---|---|---|
| E1 | Raw concrete interior; monolithic volumes; a single light shaft from above; board-formed texture | Monochrome gray world; light vs. shadow as the only "decoration"; negative space as a compositional element |
| E2 | B&W low-angle shot of a massive cantilevered block; strong horizontal banding | Weight and tension (heavy mass "floating"); photographic drama from extreme viewpoints; rhythm of repeated bands |
| E3 | B&W worm's-eye view of two curved towers with vertical fins; sky as void between them | Repetition/rhythm of structural elements; the sky as negative space; curves can coexist with brutalism |
| E4 | Near-abstract worm's-eye of a cylindrical tower; grid wrapping a curve; extreme contrast | Abstraction: architecture as pure graphic pattern; usable as hero/section background texture |
| E5 | Brutalist stacked concrete slabs overgrown with vegetation; gray + green palette | **Key for OPUS**: concrete + landscape in one frame — exactly the studio's identity (architecture *and* landscape) |

**Common threads:** monochrome photography, extreme viewpoints, mass and weight, texture of raw material, repetition/rhythm, negative space, and (E5) nature meeting concrete.

## Web references (layout, typography, color, motion)

| # | Reference | Key patterns |
|---|---|---|
| W1 | "Taishanyou" visitor-center concept (pink/black) | Giant display type bleeding off-canvas and **overlapping photos**; full-bleed color-blocked sections; coordinates (36.16N 117.6E) as graphic metadata; 3-column caption rows; project spec list (architect / year / location) |
| W2 | "Barbican Estate" concept (orange-red/off-white, by @lindademidova) | Swiss-editorial brutalism: huge condensed sans hero with photo breaking through the type; "At a glance" **spec-sheet rows with horizontal rules**; archival B&W photos; architectural drawing as faint background texture; giant pull quote; minimal top nav |
| W3 | "Monday" poster | Type rotated on diagonals, crossing the photo; type as literal structure; red accent over neutral photo. Mostly a *what-not-to-do* for UI (see below) |
| W4 | "NOBODY" poster | Single accent color (yellow) over B&W photo; type sliced and interwoven **behind** the building (masking); accent color filling the building's voids; small dense caption block |

## What to take

1. **Typography as structure.** Oversized condensed display type is the primary visual element; it may bleed off-canvas and overlap/interlock with photography (W1, W2, W4). Headlines in the 40–60vw scale territory, not "big headings".
2. **Monochrome photography + one accent color.** B&W or duotone treatment on all project photos, with a single loud accent (W2's red, W4's yellow). This (a) unifies mixed-source Pinterest imagery, (b) is token-friendly, (c) reserves the accent for the CTA → direct conversion benefit.
3. **Spec-sheet rows** (label + value + horizontal rule: location, year, type, status — W1, W2). Perfect for project detail pages and as credibility/social proof near CTAs (awards, built work).
4. **Metadata as ornament.** Coordinates, dates, project IDs in small mono type (W1) — honest "data rawness" instead of decoration.
5. **Color-blocked sections** (W1): full-bleed background changes mark section boundaries — strong scroll rhythm, cheap to build, great hook for scroll-triggered transitions.
6. **Extreme-angle B&W photography** (E2–E4) for heroes and section breaks; E5's concrete+green as the emotional image for the landscape dimension of OPUS.
7. **Pull quotes at display size** (W2) for studio voice / awards.
8. Motion implications (refs are static, inferred): type reveals on scroll, photo parallax inside type masks or section blocks, background color transitions between sections, duotone→color on hover. All `transform`/`opacity` only.

## What to avoid

1. **Rotated/diagonal body text** (W3): illegible, breaks screen readers and reading order. Rotation only as a decorative *display* accent, never for content. ⚠️ tension candidate — flag via §5.3 if it comes up.
2. **Script/handwritten type for information** (W1's coordinates, W3): fails contrast and legibility. If used at all, purely decorative and duplicated accessibly.
3. **Low-contrast color-on-color text** (W1's dark-pink-on-pink captions): every text/background pair must be checked against AA ratios.
4. **Letter-sliced photo masking on interactive elements** (W4): expensive, fragile, bad for LCP if used on the hero image. Acceptable as a static pre-rendered asset only.
5. **Showcase syndrome:** W1 and W2 have **no CTA at all** — they're portfolio art. Our version keeps one dominant `Book a consultation` per view; the accent color belongs to the CTA first, decoration second.
6. Walls of tiny caption text (W3, W4): keep microcopy short and readable.

## Direction synthesis (for low-fi and the design system)

Editorial-brutalist hybrid: Swiss grid discipline (W2) + oversized interlocking type (W1) + monochrome photography with one accent color (W4) + spec-sheet data rawness (W1/W2), over an architectural mood of mass, texture and negative space (E1–E4), with E5 anchoring the concrete-meets-landscape story that is uniquely OPUS. The accent color is the conversion channel: CTA always wins the loudness contest.

- **UX:** grid + rules keep radical type scannable; data rows give instant comprehension on mobile.
- **Conversion:** accent reserved for CTA; spec/award rows as social proof adjacent to booking entry points.

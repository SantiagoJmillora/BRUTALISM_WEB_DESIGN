# Low-fi options (F1)

> Every option stays in Figma `02 Mobile` (one section per view). This file is the text record of each option and decision.

## F1-03 · Home (mobile 390 × 844)

Status: **A approved (2026-11-12); hero tension → C (monochrome/darkened photo under text + sticky CTA from first paint).** Figma: section "F1 · Home — Low-fi mobile (F1-03)".

| | A — Monolith ★ | B — Index | C — Chapters |
|---|---|---|---|
| Idea | Photo-first, one project per screen | Type-first Swiss spec sheet | Color-blocked chapters + carousel |
| Hero | Full-bleed photo (REF #1), giant "OPUS" **behind** a building cut-out, value proposition at the bottom | Headline *is* the hero ("ARCHI—TECTURE + LAND—SCAPE"), photo band (REF #7) with "AS ONE." crossing it | Photo (REF #9) top + black block; giant "OPUS" straddling the edge; headline + CTA on the block |
| CTA in first viewport | Sticky only | Inline button; sticky after it scrolls away | Inline button; sticky after it scrolls away |
| Featured ×8 | Full-screen stacked cards (CSS sticky, native scroll) | Numbered index rows + thumbnail | Horizontal scroll-snap carousel |
| Disciplines | 2 full-bleed photo chapters | 2 text rows with rules | 2 color-blocked chapters |
| Studio | Pull quote + awards list | Facts grid (2006 · 3 partners · ~17 team · 10+ awards) | Team photo + quote |
| Length | ~4,100 px | ~3,000 px | ~3,700 px |
| UX | + Max drama, photos as protagonists, type mandate in the hero. − Long scroll | + Fastest to scan, shortest. − Photos secondary | + Strong rhythm, readable hero. − Carousels: cards 3–8 mostly unseen |
| Conversion | + Sticky always visible, proof right after hero. − Relies on sticky; final CTA far | + Explicit CTA above the fold, list → project in 1 tap. − Less emotional pull | + CTA above the fold. − Weak exposure of featured proof |

Recommendation: **A**, borrowing B's numbered index as the "All 26 projects" teaser if the page feels too long in hi-fi.

```
⚠️ TENSIÓN brutalismo vs conversión (Option A hero)
Problema: white text over a photo can fail 4.5:1 depending on the image; and the hero has no inline CTA (sticky only).
Opción A: pure photo, no treatment — costo: contrast fails on light areas (AA).
Opción B: solid block behind text (like C) — costo: loses the full-bleed monolith.
Opción C: monochrome/darkened photo treatment (duotone token) under the text zone + sticky CTA visible from first paint — costo: photos are less "natural".
Recomendación: C — consistent with the monochrome direction in references.md.
```

### F1-03b · Home A — parallax options

Status: **Combination 2 (P1 + P2) approved for mobile AND desktop (2026-11-12).** Figma: section "F1 · Home A — Parallax options (F1-03b)" (half-scale storyboards at 0 / 50 / 100 % scroll).
Rules for all: `transform`/`opacity` only · native scroll (no scroll-jacking) · `prefers-reduced-motion` → static.

| Technique | What moves | Spec |
|---|---|---|
| P1 Hero depth split | Photo + building cut-out at 0.7×, "OPUS" at 0.45× → the letters sink **behind** the building; headline fades | Scrub over hero height; cut-out PNG small (< ~80 KB) to protect LCP |
| P2 Inner image | Image (scale 1.2) inside an `overflow:hidden` card window, translateY −10% → +10% | Scrub while the card crosses the viewport; cheap, no CLS |
| P3 Horizontal type | Giant discipline word translateX 0 → −60% on vertical scroll | Scrub over chapter height, no pinning |
| P4 Stacking depth | Covered card scales 1 → 0.92 and dims 0 → 40% | Driven by the sticky stack |

| Combination | Includes | Verdict |
|---|---|---|
| 1 — Subtle | P2 | Safest perf; hero static, mandate has no motion |
| 2 — Hero depth ★ | P1 + P2 | One clear "wow" in the first scroll, calm afterwards; recommended for mobile |
| 3 — Full choreography | P1 + P2 + P3 + P4 | Richest; motion fatigue + heavier JS on mobile → reserve for desktop (F5) |

## F1-04 · Projects index (mobile 390 × 844)

Status: **A approved (2026-11-12).** Figma: section "F1 · Projects — Low-fi mobile (F1-04)".

| | A — Showcase + archive table ★ | B — Single numbered index | C — Mosaic grid |
|---|---|---|---|
| Filters | Sticky chips with OPUS's 5 categories (Housing · Culture & education · Public space · Institutional & commercial · Tourism & rural); `?type=` in URL | One "Filter" button → bottom sheet | Discipline tabs (All · Architecture · Landscape) + type dropdown |
| Featured 8 | Large 4:5 cards + spec row, P2 inner parallax | ★ rows; the row in view expands with a big image | First spans 2 columns |
| Archive 18 | Dense table (No · Project · City), rows ≥ 48 px | Same list | 2-up grid |
| End | "Planning something similar?" CTA + empty-filter state with CTA | CTA | CTA |
| UX | + Clear hierarchy, fast archive. − Two visual languages | + Consistent, short. − Featured loses its stage | + Visual. − Small thumbs, 26 images = heavy |
| Conversion | + Proof first; `?type=` feeds booking prefill; empty state converts | + Fast to any project. − Weak proof; hidden filter | − Generic, least brutalist; weight hurts speed |

Recommendation: **A** — it is IA option C made literal.

## F1-05 · Project detail (mobile 390 × 844)

Status: **B2 + B-LIGHT approved (2026-11-12); tension → C (3-fact strip under the hero + data accordion).** Figma: section "F1 · Project detail — Low-fi mobile (F1-05)".

| | A — Spec sheet first ★ | B — Editorial story | C — Immersive gallery |
|---|---|---|---|
| Structure | ← Projects · 01/08 → hero with giant name (darkened photo) → **spec sheet** → award block → 1 statement + ≤120 words → gallery (full-bleed / inset / 2-up, credits) → CTA with prefill → next project | Full-screen hero → pull quote → chapters Context · Idea · Result → spec sheet in an accordion → CTA | Full-screen scroll-snap images + bottom drawer (name, data, CTA; pull up for info) |
| UX | + Facts in the first scroll; same frame for all 8; easy to fill with verified data. − Less narrative | + Magazine reading. − Needs ~400 words/project we don't have (risk of invented copy); facts hidden | + Max photo impact. − Drawer gestures hurt keyboard/screen-reader use; scroll-snap can feel hijacked on iOS |
| Conversion | + Proof (spec + award) before the story; contextual CTA with `?type=`; next-project loop | − Proof and CTA at the very end | + CTA always in the drawer. − Little context; 21 full-screen images = heavy |

**A-LIGHT** (18 archive projects, derived from A): ← Projects → name → spec sheet → gallery → CTA. Missing data rows are hidden, never invented.

Recommendation: **A** (+ A-LIGHT).

### B2 — Editorial short (Santiago's revision of B) ★
Hero full-screen (name, back, 01/08) → **key facts strip** (Location · Status · Award) → pull quote (OPUS public text) → intro ≤ 80 words → **gallery as protagonist** (full-bleed / inset / 2-up, P2, credits) → project-data accordion → CTA with `?type=` → next project.
No Context/Idea/Result chapters: no invented long copy; the photos tell the story.

### B-LIGHT — archive template
Shorter hero (55%) → facts strip → optional ≤ 40-word intro (only if OPUS has public text) → gallery → data accordion → CTA. No quote, no next-project loop.

```
⚠️ TENSIÓN brutalismo vs conversión (B2)
Problema: with the spec sheet in an accordion, the proof (status, award) disappears from the first scroll — the user sees only photos and a quote before deciding.
Opción A: pure editorial, everything in the accordion — costo: proof invisible for most users.
Opción B: full spec sheet open after the intro — costo: breaks the editorial rhythm, a table before the photos.
Opción C: 3-fact strip under the hero (Location · Status · Award) + full data in the accordion — costo: one extra band in the hero zone.
Recomendación: C — **approved by Santiago 2026-11-12.**
```

## F1-06 · Studio / About (mobile 390 × 844)

Status: **C2 approved (2026-11-12) = B's manifesto first screen + C's timeline; tension → C: 'Latest recognition' strip after the manifesto.** Figma: section "F1 · Studio — Low-fi mobile (F1-06)".

| | A — Dossier ★ | B — Manifesto + people | C — Timeline |
|---|---|---|---|
| Structure | "Studio" + OPUS tagline → facts grid (2006 · 3 partners · ~17 team · 10+ awards) → disciplines (inverted block) → 3 partners (portrait if public + name + role) → team names (text) → awards table (year · award · project →) → clients as typographic wall (Public / Private / Real estate) → CTA | Giant manifesto with scroll reveal → full-screen partner portraits → team photo grid → awards accordion → client logo marquee → CTA | "Since 2006" → vertical timeline of verified milestones → compact partners/team/clients → CTA |
| UX | + Scannable credentials, all verifiable, little copy; awards link to projects. − Few images | + Personality, warmth. − Needs ~20 portraits of real people (may not be public); awards hidden | + Clear story. − Depends on dates we can't verify; latest wins at the bottom |
| Conversion | + Strongest credibility for institutions, public and developers | + Trust through faces. − Proof buried; client logos = trademark risk on an unofficial site | + "Trajectory". − Proof ordered by time, not relevance |

Recommendation: **A**.

### C2 — Manifesto + timeline (Santiago's merge of B + C) ★
Manifesto screen ("WE DESIGN THE BUILDING AND THE PLACE AROUND IT." — concept copy, value proposition #2, not attributed to OPUS) → *latest recognition* strip → "Since 2006" timeline with verified milestones only (2006 founding · 2016 Karl Brunner · 2018 BLAP + Quito · 2019 Harvard GSD · 2023 CEMEX + PLAH+ · 2024 WAF + IAA · 2025 AR + ArchDaily finalist), milestones link to projects; spine draws on scroll → partners · team · clients as text lists → "Your project could be next." CTA.

```
⚠️ TENSIÓN brutalismo vs conversión (C2)
Problema: a chronological timeline puts the strongest, most recent proof (WAF 2024, 2025 awards) at the bottom of the story.
Opción A: pure chronology 2006 → 2025 — costo: latest wins seen only by those who scroll to the end.
Opción B: reverse chronology 2025 → 2006 — costo: loses the "20-year journey" narrative Santiago wants.
Opción C: chronology + a one-line "Latest recognition" strip right after the manifesto — costo: the latest awards appear twice.
Recomendación: C — **approved by Santiago 2026-11-12.**
```

## F1-07 · Booking (mobile 390 × 844)

Status: **options proposed, awaiting approval.** Figma: section "F1 · Booking — Low-fi mobile (F1-07)". Flow A from F1-02 (project → time → details).

| | A — Full-page steps + fixed bottom bar ★ | B — Conversational | C — Summary rail |
|---|---|---|---|
| Layout | Progress 1/3 + step name, concept notice line, one big question per step, ≥ 48 px chips/slots, fixed bar (← Back · Continue) | One question per screen, 7 micro-screens, auto-advance | Dark summary rail at top fills in; inline "Next ↓" buttons |
| UX | + Focus, thumb-zone actions, clear progress. − Bar takes 84 px | + Engaging. − 1/7 feels long; harder to review | + Always see choices. − Rail eats ~96 px; button below fold on step 2 |
| Conversion | + No nav/footer distractions; summary before submit | + High start. − 7 drop-off points; stretches "≤ 3 steps" | − Primary action hidden on mobile |

States drawn for A: step 1 (type prefilled via `?type=`, stage, message 0/280) · step 2 (14-day strip, 3-col slots, GMT−5, step-1 summary ✎) · step 3 (name, email, summary, "Book consultation") · confirmed (recap, what happens next, .ics, back to projects) · error slot taken (alert + greyed slot, data kept) · validation error (summary + inline, not color-only) · **no times** (pending decision: jump to next available date; if none, honest message + link to Projects).

Recommendation: **A**.

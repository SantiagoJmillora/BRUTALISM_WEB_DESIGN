# Conversion strategy (F0-07)

> Business layer of the redesign: who we convert, with what promise, against which objections, through which funnel.
> All OPUS facts come from `content-sources.md`. Anything that is a **concept decision** (not an OPUS fact) is labelled as such.

## 1. Audiences

| # | Segment | Evidence in OPUS's work | What they need to decide | Role in the funnel |
|---|---|---|---|---|
| A | **Private clients** — families building a house, mostly Oriente Antioqueño | Casa La Pausa, Casa GOZU, several houses in El Retiro / Rionegro | "Do they do projects my size? Will they listen to me?" | **Primary booker** |
| B | **Developers & companies** — real estate, corporate, commercial | Conconcreto, Colpatria clients; NOVA–CELSIA, Oviedo, Obra19, BIO26, Lote32 | Track record of *built* work, delivery, value added to the asset | **Primary booker** |
| C | **Institutions** — universities, family-compensation funds, foundations | UdeM, UPB, Uninorte, COMFAMA, Fundación Santo Domingo; MOVA, CEFE Las Cometas | Awards, comparable typologies (education, health, culture), process | **Secondary booker** |
| D | **Public entities** — ministries, governments, FINDETER | Ministerio de Cultura, Gobernación de Antioquia; Albarrada de Mompox, Barranquilla historic centre | Credentials and references; they hire through tenders and competitions | **Not a booker** — credibility audience |

**Decision:** the booking flow is designed for A + B (C fits without changes). D is served by proof (awards, public projects), not by the booking form.

## 2. Value proposition

**Core claim:** OPUS designs the building **and** the place around it — architecture and landscape as one discipline, proven by internationally awarded built work.

- Why it's true: three disciplines in one office (architecture, landscape & urban design, other design) and awards on both sides: WAF 2024 category winner (Hospital Tatamá, architecture) and the BLAP Gran Premio 2018 (Albarrada de Mompox, landscape).
- Why it matters to the client: one team for the building, its outdoor space and its relationship to the city or land → a coherent result and fewer interfaces to manage.
- Differentiator vs. other Medellín offices: the landscape half. Most studios show buildings; OPUS shows buildings *in places*.

**Headline candidates (EN, to be tested in hi-fi):**
1. "Architecture and landscape, designed as one."
2. "We design the building — and the place around it."
3. "Buildings that belong to their place."

Recommendation: **#1**. It is the shortest, it states the differentiator without adjectives and it fits giant display type.

**Proof strip (always next to the primary CTA):** `WAF 2024 · Category Winner` · `BLAP 2018 · Gran Premio` · `ArchDaily Building of the Year 2025 · Finalist` · `Since 2006 · Medellín`.

## 3. Objections → answers on the site

| Objection | Segment | Answer (where) |
|---|---|---|
| "They only do big public projects; I'm too small." | A | Homes visible on Home and filterable on Projects; project-type options in booking include "House" |
| "Have they actually *built* things, or only competitions?" | B, C | A `Built / In design / Competition` status on every project card and spec sheet |
| "Will it be expensive / is the first meeting paid?" | A, B | Concept decision: describe the consultation as a "30-min intro call" with no commitment. Fees are **not** stated (no public data; never invented) |
| "I don't have plans or land yet — too early to call?" | A | Microcopy in booking step 1: "Any stage — from an idea to a plot to a brief." |
| "What happens after I book?" | All | A 3-line "What happens next" block on the booking page and the confirmation screen |
| "Is this the real OPUS site?" | All | Mandatory notice: "Concept project — bookings are not sent to OPUS." (see §7 tension) |

## 4. Funnel

```
Discovery (Instagram, ArchDaily, referral, portfolio link — site is noindex)
  → HOME: understand in 3 s (hero photo + headline + proof strip + CTA)
    → PROJECTS: self-identify (filter by type: Housing, Education & Culture, Public space, Commercial, Landscape)
      → PROJECT DETAIL: proof (spec sheet + award + status) → contextual CTA
        → BOOKING (3 steps) → CONFIRMATION
```

- **Shortcut:** the sticky mobile CTA lets a convinced user skip straight to Booking from any view.
- **Contextual CTA on project detail:** "Planning something similar?" + `Book a consultation`, with the project type pre-filled in step 1 (removes one decision).

### Booking — 3 steps (concept decision, feeds F1-02)
1. **Your project:** type (chips) + stage (optional chips) + short message (optional)
2. **Pick a time:** free slots shown in America/Bogota time
3. **Your details:** name + email → confirm

The order is deliberate: commitment grows gradually (foot-in-the-door), so the easy, engaging question comes first and personal data comes last, which lowers abandonment at the step that feels most like a form. The fields are the CLAUDE.md minimum plus one optional "stage" chip (one tap, no typing). It qualifies leads for the admin at almost no friction cost.

## 5. CTA rules

- One label everywhere: **`Book a consultation`** (no variants, so it builds recognition). Context goes in the line above, not in the button.
- The accent color is reserved for the CTA (see `references.md`): it always wins the loudness contest.
- Placement: hero; sticky bar on mobile, hidden while the booking page or the footer CTA is in view; end of every project detail; footer.
- Proof is never more than one scroll away from a CTA.

## 6. Metrics (for the case study)

| Metric | Definition |
|---|---|
| CTA click-through | CTA clicks / sessions, split by placement (hero, sticky, project, footer) |
| Booking start → complete | Step 1 views → confirmations; drop-off per step |
| Project → booking | Share of bookings that come from a project-detail CTA |
| Speed | LCP / INP budgets from CLAUDE.md §8.4 (speed = conversion) |

Implementation: privacy-friendly analytics (e.g. Vercel Analytics custom events). The choice of tool is made in F6/F7; it needs approval if it adds a dependency.

## 7. Tensions

**Resolved 2026-11-12 (Santiago): both → Option C.**

```
⚠️ TENSIÓN brutalismo/ética vs conversión
Problema: the mandatory "Concept project — bookings are not sent to OPUS." notice adds doubt at the moment of commitment.
Opción A: notice as a loud banner on every view — costo: competes with the CTA, lowers trust site-wide.
Opción B: notice only in the footer — costo: violates CLAUDE.md §11 (must be visible in booking).
Opción C: fixed, readable line inside the booking flow (step 1 and confirmation) + footer disclaimer — costo: small drop in booking completion.
Recomendación: C. It complies with §11, stays honest at the exact moment it matters, and doesn't pollute discovery.
```

```
⚠️ TENSIÓN brutalismo vs conversión
Problema: giant display type + full-bleed photo hero can push the CTA and proof strip below the fold at 390×844.
Opción A: type-only hero, CTA below the fold — costo: no conversion path in the first 3 s.
Opción B: conventional hero with a small headline — costo: loses the brutalist identity.
Opción C: giant type over the photo + sticky CTA always visible + proof strip as the first element after the hero — costo: less vertical room for the photo.
Recomendación: C.
```

## 8. Implications for the next phases

- **F1-01 (IA):** Projects needs type filters matching the segments; a Studio page carries the awards/clients proof for C and D.
- **F0-08 (featured projects):** the selection should cover A (a house), B (commercial/corporate), C (education/health) and the landscape story (Mompox), with built work first.
- **F1-07 (booking):** the 3 steps above, the project-type pre-fill and "What happens next".

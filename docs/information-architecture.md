# Information architecture (F1-01)

> Status: **Option C approved (2026-11-12).** Discarded options stay here and in Figma (`02 Mobile`) as process record.
> Shared by all options: `/admin/login` · `/admin` (bookings list) · `/admin/bookings/[id]` · `/admin/availability`; footer with disclaimer; sticky `Book a consultation` on mobile.

## Option A — One-page narrative
```
/                 Hero → Proof strip → 8 featured (inline) → Landscape story (Mompox) → Studio + awards → Booking (inline, 3 steps)
/projects/[slug]  8 detail pages (featured only)
```
- Idea: one long scroll tells the whole story and ends in the form.
- UX: + zero navigation decisions, strong scroll storytelling for motion. − Very long on mobile; the booking is hard to reach without the sticky CTA; deep links to "Studio" are anchors only.
- Conversion: + the form is the natural end of the story. − Inline form inherits a long page's weight (LCP, JS); no dedicated, distraction-free booking route; hard to measure per-section.
- Content: only 8 projects → least content work.

## Option B — Classic multipage
```
/                    Hero → Proof strip → Featured teaser (3) → CTA
/projects            Index of 26 + filters by type
/projects/[slug]     26 detail pages
/studio              About, team, awards, clients
/book                3 steps → /book/confirmed
```
- Idea: conventional architecture-office structure, everything has its own page.
- UX: + predictable, every page deep-linkable, scales. − The Home is thin, so the "wow" depends on clicking further; 26 detail pages are a lot of thin content (several projects have few images or text).
- Conversion: + dedicated booking route, easy funnel metrics. − More pages between interest and CTA; proof is spread out.
- Content: 26 projects → most content work.

## Option C — Hybrid (narrative home + depth on demand) ★
```
/                    Hero → Proof strip → 8 featured (big, scroll-driven) → Disciplines (Architecture · Landscape) → Studio teaser + awards → CTA
/projects            Index: 8 featured first (large) + remaining 18 as a compact "Archive" list with filters
/projects/[slug]     Full detail for the 8 featured; archive items open a lightweight detail (gallery + spec sheet)
/studio              Team, awards, clients (credibility for institutions and public entities)
/book                3 steps (prefill ?type= from project CTA) → /book/confirmed
```
- Idea: the Home carries the story and the proof; depth is there for those who want it; booking is its own focused route.
- UX: + 3-item nav (Projects · Studio · Book), Home understood in 3 s, scales to 26 projects without 26 heavy pages. − Two detail templates (full + light) to design.
- Conversion: + proof + featured on Home → CTA within one scroll; distraction-free `/book`; project → booking prefill removes a decision; clean funnel metrics per route.
- Content: 8 full write-ups + 18 light entries (data from the manifest + public text).

**Recommendation: C.** It keeps the brutalist storytelling of A on the Home, has the clarity and metrics of B, and the 8/18 split matches the material we actually have.

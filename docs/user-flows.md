# User flows (F1-02)

> Status: **approved 2026-11-12 — Booking A · Admin C · confirm/cancel emails · 30-min consultation.** Builds on `conversion-strategy.md` §4 and `information-architecture.md` (Option C).
> Consultation = 30-min intro call (concept decision). Times stored in UTC, shown in America/Bogota.

## Booking flow

### Option A — Project first ★
```
Entry (CTA anywhere | project CTA → ?type= prefilled)
 → 1 YOUR PROJECT   type (chips, required) · stage (chips, optional) · message (optional, 280 chars)
 → 2 PICK A TIME    next 14 days, day strip + free slots
 → 3 YOUR DETAILS   name · email · honeypot (hidden) · summary of 1+2 · [Book consultation]
 → /book/confirmed  "Request received" · what happens next (3 lines) · add to calendar (.ics) · concept notice
```
- UX: easy, engaging question first; personal data last; progress "1/3" always visible; back keeps data.
- Conversion: foot-in-the-door (commitment grows step by step); the project prefill skips a decision; a summary before submitting reduces anxiety.

### Option B — Time first (Calendly-style)
```
 → 1 PICK A TIME → 2 DETAILS + PROJECT (one long step) → /book/confirmed
```
- UX: + 2 steps only; fast for users who already know they want a call. − Step 2 becomes a long form on mobile; the slot is chosen with no context.
- Conversion: + fewer steps. − Opens with the hardest decision (my calendar), so drop-off concentrates early; we lose the qualifying data that makes the admin's job easier.

### Option C — Single progressive page
```
 /book: [Project ▾] → [Time ▾] → [Details ▾] accordion on one screen → inline confirmation
```
- UX: + no page changes; the whole flow is visible. − Long scroll on 390 px; focus management and error states are harder to make accessible; the back button behaves unexpectedly.
- Conversion: + feels short. − No per-step metrics; heavy single view.

**Recommendation: A.** It is what the strategy already defined, the one that is easiest to make accessible, and it allows funnel measurement per step.

### States (apply to the chosen option)
| State | Behavior |
|---|---|
| Validation error | Inline under the field + error summary at the top of the step with focus moved to it; data is kept |
| Slot taken meanwhile (race) | On submit, the DB unique constraint rejects → back to step 2 with "That time was just booked — pick another", steps 1/3 kept |
| No slots in 14 days | Empty state: "No times available right now" + `mailto`-free fallback: leave email to be notified `[decide in F1-07]` |
| Rate limit / spam | Generic "Something went wrong, try again in a minute" (never reveal the honeypot) |
| Server down | Retry button; form data kept in memory |

### Emails (status changes)
| Trigger | To user | To admin |
|---|---|---|
| Booking created (`pending`) | "Request received" + details + concept notice | "New request" + link to `/admin/bookings/[id]` |
| Admin confirms | "Confirmed" + .ics | — |
| Admin cancels | "Cancelled" + link to book again | — |

> CLAUDE.md §8.3 requires only the first row; confirm/cancel emails **approved by Santiago (2026-11-12)** because a `pending` booking without follow-up leaves the user hanging. Cost: 2 extra React Email templates.

## Admin flow (mobile-first, single admin)

### Option A — List first
```
/admin/login → /admin: tabs [Pending | Confirmed | Cancelled] → /admin/bookings/[id] → Confirm | Cancel
            → /admin/availability: list of slots by day · add slot · delete free slot
```
- UX: + simplest to build and to use one-handed. − No sense of the week; availability is managed slot by slot.
- Effort: lowest.

### Option B — Calendar first
```
/admin/login → /admin: week agenda (free slots + bookings in one grid) → tap → detail / actions; tap empty → add slot
```
- UX: + everything in one view, visual. − A week grid on 390 px is cramped; tap targets ≥ 44 px are hard to fit.
- Effort: highest (a custom calendar component).

### Option C — Inbox + agenda ★
```
/admin/login → /admin:
   ① NEEDS ACTION: pending bookings (count badge), oldest first → detail → Confirm | Cancel
   ② UPCOMING: confirmed, grouped by day (agenda list)
 → /admin/bookings/[id]: client, project type/stage, message, time (Bogota), actions
 → /admin/availability: day list + "Add slots": date + from–to + 30-min split (bulk) · delete free slot
```
- UX: + puts what needs action first (inbox zero); the agenda list works at 390 px; creating slots in bulk saves dozens of taps.
- Effort: low–medium (lists only, no calendar grid).

**Recommendation: C.** It has nearly the effort of A, with a better daily workflow, and it stays readable on mobile.

### Admin rules (all options)
- Cancelling or confirming asks for confirmation inline (no browser `confirm()`), and both are reversible only by booking again.
- A slot with a booking can't be deleted; cancelling a booking frees its slot.
- Every action is a server-side session check + Zod; status flows only `pending → confirmed | cancelled`.

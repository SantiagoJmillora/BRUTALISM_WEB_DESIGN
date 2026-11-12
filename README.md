# OPUS — Brutalist Web Redesign

> **Unofficial concept redesign. Not affiliated with or endorsed by OPUS.**

A complete, unsolicited redesign of the website of [OPUS](http://opusestudio.com), an architecture, design and landscape studio based in Medellín, Colombia. Built as a portfolio case study: web brutalism with intention, a single dominant conversion goal (*Book a consultation*), and a full-stack implementation with an admin panel for appointments.

## Status

🚧 **In progress — Phase 0: setup & discovery.** Design happens in Figma (mobile first, gated approvals per phase) before any production code is written. See [`BACKLOG.md`](./BACKLOG.md) for the full roadmap and [`docs/case-study.md`](./docs/case-study.md) for the evolving case study.

## Concept

Web brutalism, with purpose: show only what is necessary, and make it loud. Radical hierarchy, typography as structure, honest rawness — never at the expense of usability, accessibility (WCAG 2.2 AA) or conversion.

## Planned stack

| Layer | Choice |
|---|---|
| Framework | Next.js (App Router) + TypeScript (strict) |
| Styling | Tailwind CSS v4 + design tokens (`tokens.css`, synced with Figma) |
| Animation | GSAP + ScrollTrigger, Lenis smooth scroll (disabled with `prefers-reduced-motion`) |
| Database | Postgres on Neon + Drizzle ORM |
| Auth | Better Auth (single admin) |
| Email | Resend + React Email |
| Validation | Zod |
| Testing | Vitest (unit) + Playwright (e2e) |
| Deploy | Vercel |

## Disclaimer

This is a concept project for portfolio purposes. Bookings made on the demo site are **not** sent to OPUS. Production deployments use `robots: noindex`. All project data comes from public sources (credited in [`docs/content-sources.md`](./docs/content-sources.md)); image credits live in [`docs/assets-credits.md`](./docs/assets-credits.md).

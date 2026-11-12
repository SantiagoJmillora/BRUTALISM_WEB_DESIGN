# BACKLOG — OPUS · Brutalist Web Redesign

**Leyenda:** `[ ]` pendiente · `[~]` en curso (solo una a la vez) · `[x]` hecha · `[!]` bloqueada (indicar por qué)
**IDs:** `F<fase>-<n>`. Las ramas usan el ID: `feat/F6-03-booking-form`.
**Gate:** ✅ significa que requiere el "aprobado" explícito de Santiago antes de pasar a la siguiente tarea.

---

## ▶ Now
- **Fase activa:** F0 — Setup y discovery
- **Siguiente paso exacto:** F0-04 (Figma por navegador, 3 opciones de organización) — requiere sesión con Claude in Chrome. Alternativa sin navegador: F0-06 (Santiago comparte su auditoría de opusestudio.com)
- **Bloqueos:** —
- **Bloqueos:** —

## 📥 Inbox (ideas o trabajo nuevo sin clasificar)
- —

---

## F0 — Setup y discovery
- [x] **F0-01** Inicializar el repo en `C:\dev\Proyecto brutalista` y conectarlo a `origin` (BRUTALISM_WEB_DESIGN). Agregar `.gitignore` (Node/Next), `.gitattributes` (`* text=auto eol=lf`), `.nvmrc` (Node LTS actual) y `.claude/settings.json` (sin atribución). Primer commit `chore: initial project setup`.
  - *Acepta:* `git log` sin co-autoría de Claude; el push queda en GitHub.
- [x] **F0-02** README inicial (inglés): descripción, disclaimer "Unofficial concept redesign…", estado del proyecto y stack previsto.
- [x] **F0-03** Crear la estructura `docs/` con DECISIONS, references, design-system, content-sources, assets-credits y case-study (plantillas vacías).
- [ ] **F0-04** Verificar el acceso a Figma por navegador (Claude in Chrome) y proponer **3 opciones** para organizar el trabajo en **3 páginas** (límite del plan gratuito). ✅
- [x] **F0-05** Analizar las referencias (ESTRUCTURALES y WEB) **una sola vez** y escribir `docs/references.md`: patrones, layouts, tipografía, motion, qué tomar y qué evitar.
- [ ] **F0-06** Recoger los hallazgos de la auditoría que Santiago ya hizo de opusestudio.com y complementarlos: problemas de UX y conversión, inventario de contenido (servicios, proyectos, premios, equipo) y tono. Registrar fuentes en `content-sources.md`.
- [ ] **F0-07** Estrategia de conversión: públicos objetivo (privados, desarrolladores o constructoras, entidades públicas), propuesta de valor, objeciones y embudo hasta "Book a consultation". ✅
- [ ] **F0-08** Selección de proyectos destacados (6–8) con criterio de narrativa y prueba social; Santiago aporta las imágenes y se registran los créditos. ✅

## F1 — Low-fi MOBILE
- [ ] **F1-01** Arquitectura de información y sitemap: 3 opciones (p. ej. one-page larga vs. multipágina vs. híbrida). ✅
- [ ] **F1-02** User flow del booking (≤ 3 pasos) y del panel de admin: 2–3 opciones. ✅
- [ ] **F1-03** Low-fi **Home** mobile: 3 opciones. ✅
- [ ] **F1-04** Low-fi **Projects** (listado + filtros) mobile: 3 opciones. ✅
- [ ] **F1-05** Low-fi **Project detail** mobile: 3 opciones. ✅
- [ ] **F1-06** Low-fi **Studio / About** mobile: 3 opciones. ✅
- [ ] **F1-07** Low-fi **Booking** (pasos + confirmación + estados de error y vacío) mobile: 3 opciones. ✅
- [ ] **F1-08** Low-fi **Admin** (login, agenda, detalle de cita, disponibilidad) mobile: 2–3 opciones. ✅
- [ ] **F1-09** Registrar en DECISIONS las opciones elegidas y las descartadas (estas quedan en Figma).

## F2 — Design system
- [ ] **F2-01** Tipografía: 3 combinaciones con licencia web y escala fluida. ✅
- [ ] **F2-02** Color: 3 paletas con ratios de contraste AA documentados. ✅
- [ ] **F2-03** Grid y espaciado (mobile y desktop): 3 propuestas y la escala de espaciado. ✅
- [ ] **F2-04** Lenguaje de motion: 3 propuestas (duraciones, easings, patrones de parallax y transición) + reglas de reduced-motion. ✅
- [ ] **F2-05** Montar los tokens en Figma (Variables o Styles) y documentarlos en `design-system.md` con la convención de nombres de CLAUDE.md §6.2.
- [ ] **F2-06** Componentes base en Figma: botón o CTA (estados), link, input y select (estados y error), card de proyecto, nav, sticky CTA, footer con disclaimer, tag o filtro, slot de horario. ✅

## F3 — Hi-fi MOBILE
- [ ] **F3-01** Home ✅
- [ ] **F3-02** Projects ✅
- [ ] **F3-03** Project detail ✅
- [ ] **F3-04** Studio / About ✅
- [ ] **F3-05** Booking (todos los estados) ✅
- [ ] **F3-06** Admin ✅
- [ ] **F3-07** Revisión cruzada UX + CRO + accesibilidad (contraste, targets, foco), con tensiones según el protocolo de §5.3. ✅

## F4 — Prototipo MOBILE
- [ ] **F4-01** Prototipo del flujo principal: Home → Project → Booking → Confirmación. ✅
- [ ] **F4-02** Specs de motion por sección (trigger, propiedad, duración, easing y versión reduced-motion). ✅

## F5 — DESKTOP (low-fi → hi-fi → prototipo)
- [ ] **F5-01** Low-fi desktop de las vistas clave: opciones de adaptación (no un simple estirado del mobile). ✅
- [ ] **F5-02** Ajustar grid, escala tipográfica y tokens para desktop.
- [ ] **F5-03** Hi-fi desktop de todas las vistas. ✅
- [ ] **F5-04** Prototipo desktop y specs de motion (parallax más rico que en mobile). ✅
- [ ] **F5-05** Capturas de F1–F5 a `docs/img/` y sección de diseño de `case-study.md`.

## F6 — Frontend
- [ ] **F6-01** Scaffold de Next.js + TS strict + Tailwind v4 + ESLint/Prettier + pnpm (verificando versiones actuales). Deploy inicial a Vercel (preview).
- [ ] **F6-02** `tokens.css` + `@theme`, idéntico a los tokens de Figma; fuentes con `next/font`.
- [ ] **F6-03** Layout global: nav, sticky CTA mobile, footer con disclaimer, `noindex`, metadata base.
- [ ] **F6-04** Componentes UI base (de F2-06), con estados y accesibilidad.
- [ ] **F6-05** Capa de motion: provider de GSAP + ScrollTrigger + Lenis, hook de reduced-motion y limpieza al desmontar.
- [ ] **F6-06** Home.
- [ ] **F6-07** Projects + Project detail. Los datos de proyectos se definen como contenido tipado en `src/content/` (sin CMS en el MVP).
- [ ] **F6-08** Studio / About.
- [ ] **F6-09** UI del booking con datos simulados (validación Zod en el cliente y todos los estados).
- [ ] **F6-10** Responsive desktop completo según F5.
- [ ] **F6-11** Revisión de rendimiento parcial (imágenes, LCP del hero, CLS de las fuentes).

## F7 — Backend (panel de admin de citas)
- [ ] **F7-01** Neon Postgres vía Vercel + Drizzle: esquema `admin_user`, `availability_slot` y `booking` (estado, datos del cliente, tipo de proyecto, mensaje). Restricción única para evitar dobles reservas. Migración + seed.
- [ ] **F7-02** Better Auth: login de un único admin; rutas `/admin/*` protegidas en el servidor.
- [ ] **F7-03** CRUD de disponibilidad (crear, eliminar y ver horarios). UTC en la base de datos y `America/Bogota` en la UI.
- [ ] **F7-04** Server Action de reserva: Zod, verificación de que el slot esté libre, transacción, honeypot y rate limit.
- [ ] **F7-05** Conectar la UI del booking (F6-09) al back real.
- [ ] **F7-06** Emails con Resend + React Email: confirmación al usuario y aviso al admin.
- [ ] **F7-07** Dashboard del admin: lista de citas (pendientes, confirmadas, canceladas), detalle, confirmar y cancelar.
- [ ] **F7-08** `.env.example` completo y variables configuradas en Vercel (preview y producción).

## F8 — QA
- [ ] **F8-01** Unit tests (Vitest): lógica de slots, validaciones y transiciones de estado.
- [ ] **F8-02** E2E (Playwright): reserva completa, intento de doble reserva y login + confirmación desde el admin.
- [ ] **F8-03** Accesibilidad: axe, navegación por teclado, lector de pantalla básico y reduced-motion.
- [ ] **F8-04** Lighthouse mobile y desktop según los presupuestos de §8.4; corregir lo que falle.
- [ ] **F8-05** Pruebas en dispositivos reales (iOS Safari y Android Chrome) y en ambos PCs.

## F9 — Lanzamiento y portafolio
- [ ] **F9-01** Deploy a producción en Vercel desde `main`.
- [ ] **F9-02** README final: screenshots, GIF de motion, stack, decisiones clave, cómo correrlo localmente y disclaimer.
- [ ] **F9-03** `case-study.md` completo (incluye la evaluación de la experiencia con Fable).
- [ ] **F9-04** Material para portafolio y LinkedIn (capturas y mockups). ✅

## 🧊 Futuro (fuera del MVP)
- [ ] Sincronizar las citas con Google Calendar.
- [ ] Versión en español (i18n).
- [ ] CMS headless para proyectos.
- [ ] Si se le ofrece a OPUS: reemplazar todas las imágenes por material licenciado de OPUS, quitar `noindex` y el aviso de concepto, y conectar sus canales reales.

---

## 🗒 Session log
<!-- Una línea por sesión: YYYY-MM-DD · qué se hizo · siguiente paso -->
- 2026-11-12 · Proyecto definido: empresa OPUS, CLAUDE.md y backlog creados · Siguiente: F0-01
- 2026-11-12 · F0-01/02/03: repo inicializado (main, Node 24, sin atribución), README con disclaimer, estructura docs/ con plantillas · Siguiente: F0-04 (push pendiente de OK)
- 2026-11-12 · F0-05: 9 referencias analizadas y resumidas en docs/references.md (dirección: editorial-brutalista, foto monocroma + 1 acento reservado al CTA) · Siguiente: F0-04 o F0-06

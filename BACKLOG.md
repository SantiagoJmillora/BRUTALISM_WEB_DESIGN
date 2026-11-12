# BACKLOG — OPUS · Brutalist Web Redesign

**Leyenda:** `[ ]` pendiente · `[~]` en curso (solo una a la vez) · `[x]` hecha · `[!]` bloqueada (indicar por qué)
**IDs:** `F<fase>-<n>`. Las ramas usan el ID: `feat/F6-03-booking-form`.
**Gate:** ✅ significa que requiere el "aprobado" explícito de Santiago antes de pasar a la siguiente tarea.

---

## ▶ Now
- **Fase activa:** F3 — Hi-fi MOBILE
- **Siguiente paso exacto:** aprobación de F3-02 (Projects hi-fi) → F3-03 Project detail (B2 + B-LIGHT)
- **Figma:** archivo "Campo de prueba" con páginas `01 Foundations` · `02 Mobile` · `03 Desktop` (Chrome conectado y funcionando). Las secciones se crean al empezar cada fase.
- **Pendiente de Santiago:** —
- **Bloqueos:** —

## 📥 Inbox (ideas o trabajo nuevo sin clasificar)
- Logo OPUS en SVG (vectorizar el webp o pedir el original) antes de F6.
- Hero WebP con alfa del recorte (≤ 150 KB @ 1200 px) en F6.

---

## F0 — Setup y discovery
- [x] **F0-01** Inicializar el repo en `C:\dev\Proyecto brutalista` y conectarlo a `origin` (BRUTALISM_WEB_DESIGN). Agregar `.gitignore` (Node/Next), `.gitattributes` (`* text=auto eol=lf`), `.nvmrc` (Node LTS actual) y `.claude/settings.json` (sin atribución). Primer commit `chore: initial project setup`.
  - *Acepta:* `git log` sin co-autoría de Claude; el push queda en GitHub.
- [x] **F0-02** README inicial (inglés): descripción, disclaimer "Unofficial concept redesign…", estado del proyecto y stack previsto.
- [x] **F0-03** Crear la estructura `docs/` con DECISIONS, references, design-system, content-sources, assets-credits y case-study (plantillas vacías).
- [x] **F0-04** Verificar el acceso a Figma por navegador (Claude in Chrome) y proponer **3 opciones** para organizar el trabajo en **3 páginas** (límite del plan gratuito). ✅
- [x] **F0-05** Analizar las referencias (ESTRUCTURALES y WEB) **una sola vez** y escribir `docs/references.md`: patrones, layouts, tipografía, motion, qué tomar y qué evitar.
- [x] **F0-06** Recoger los hallazgos de la auditoría que Santiago ya hizo de opusestudio.com y complementarlos: problemas de UX y conversión, inventario de contenido (servicios, proyectos, premios, equipo) y tono. Registrar fuentes en `content-sources.md`.
- [x] **F0-07** Estrategia de conversión: públicos objetivo (privados, desarrolladores o constructoras, entidades públicas), propuesta de valor, objeciones y embudo hasta "Book a consultation". ✅
- [x] **F0-08** Selección de proyectos destacados (6–8) con criterio de narrativa y prueba social; Santiago aporta las imágenes y se registran los créditos. ✅

## F1 — Low-fi MOBILE
- [x] **F1-01** Arquitectura de información y sitemap: 3 opciones (p. ej. one-page larga vs. multipágina vs. híbrida). ✅
- [x] **F1-02** User flow del booking (≤ 3 pasos) y del panel de admin: 2–3 opciones. ✅
- [x] **F1-03** Low-fi **Home** mobile: 3 opciones. ✅
- [x] **F1-04** Low-fi **Projects** (listado + filtros) mobile: 3 opciones. ✅
- [x] **F1-05** Low-fi **Project detail** mobile: 3 opciones. ✅
- [x] **F1-06** Low-fi **Studio / About** mobile: 3 opciones. ✅
- [x] **F1-07** Low-fi **Booking** (pasos + confirmación + estados de error y vacío) mobile: 3 opciones. ✅
- [x] **F1-08** Low-fi **Admin** (login, agenda, detalle de cita, disponibilidad) mobile: 2–3 opciones. ✅
- [x] **F1-09** Registrar en DECISIONS las opciones elegidas y las descartadas (estas quedan en Figma).

## F2 — Design system
- [x] **F2-01** Tipografía: 3 combinaciones con licencia web y escala fluida. ✅
- [x] **F2-02** Color: 3 paletas con ratios de contraste AA documentados. ✅
- [x] **F2-03** Grid y espaciado (mobile y desktop): 3 propuestas y la escala de espaciado. ✅
- [x] **F2-04** Lenguaje de motion: 3 propuestas (duraciones, easings, patrones de parallax y transición) + reglas de reduced-motion. ✅
- [x] **F2-05** Montar los tokens en Figma (Variables o Styles) y documentarlos en `design-system.md` con la convención de nombres de CLAUDE.md §6.2.
- [x] **F2-06** Componentes base en Figma: botón o CTA (estados), link, input y select (estados y error), card de proyecto, nav, sticky CTA, footer con disclaimer, tag o filtro, slot de horario. ✅

## F3 — Hi-fi MOBILE
- [x] **F3-01** Home ✅
- [~] **F3-02** Projects ✅
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
- 2026-11-12 · F0-06: auditoría de Santiago registrada (falta "magia", mandato de letras delante/detrás) + inventario completo de opusestudio.com (proyectos, premios, equipo, clientes, tono) en content-sources.md y case-study.md · Siguiente: F0-04
- 2026-11-12 · F0-04: opción B aprobada (por plataforma); páginas creadas en Figma vía Chrome; opciones registradas en DECISIONS · Siguiente: F0-07
- 2026-11-12 · F0-07 redactado (docs/conversion-strategy.md, 2 tensiones pendientes); 545 imágenes de 26 proyectos descargadas de opusestudio.com a assets-src/ (gitignored) con manifest; fotos E1–E5 registradas como candidatas al hero · Siguiente: tensiones F0-07 → F0-08
- 2026-11-12 · F0-07 cerrado (tensiones → C); F0-08: 8 destacados (6 de Santiago + Mompox y Tatamá); hero = OPUS REF #1, #7, #8, #9 · Siguiente: F1-01
- 2026-11-12 · F1-01: IA híbrida (C) aprobada; 3 sitemaps dibujados en Figma `02 Mobile` › sección "F1 · IA — Sitemaps (F1-01)" vía Plugin API desde Chrome · Siguiente: F1-02
- 2026-11-12 · F1-02: booking A (proyecto primero) + admin C (bandeja + agenda) + emails de confirmar/cancelar + consulta de 30 min; flujos dibujados en Figma `02 Mobile` › "F1 · Flows — Booking & Admin (F1-02)" · Siguiente: F1-03
- 2026-11-12 · F1-03: Home A (Monolith) + tensión hero → C + parallax combinación 2 (P1+P2) en mobile y desktop · Siguiente: F1-04
- 2026-11-12 · F1-04: Projects A (destacados + tabla de archivo, filtros ?type=) · Siguiente: F1-05
- 2026-11-12 · F1-05: detalle B2 (editorial corta, galería protagonista) + B-LIGHT + franja de 3 datos (tensión C) · Siguiente: F1-06
- 2026-11-12 · F1-06: Studio C2 (manifiesto + timeline 20 años) + franja Latest recognition · Siguiente: F1-07
- 2026-11-12 · F1-07: Booking A (pasos a pantalla completa + barra fija, 7 estados) + sin horarios → próxima fecha · Siguiente: F1-08
- 2026-11-12 · F1-08/09: Admin A (+ repetir 4 semanas); low-fi mobile cerrado; descartes movidos a `01 Foundations` (Archive), `02 Mobile` solo con lo aprobado · Siguiente: F2-01
- 2026-11-12 · F2-01: tipografía A (Barlow Condensed + Barlow + IBM Plex Mono) + escala fluida de 9 tokens · Siguiente: F2-02
- 2026-11-12 · F2-02: color A con acento #FF5B14 (borde de tinta en claro, overlay 65%) · Siguiente: F2-03
- 2026-11-12 · F2-03: grid A (suizo 4/12, base 4) · Siguiente: F2-04
- 2026-11-12 · F2-04: motion A (mecánico) · Siguiente: F2-05
- 2026-11-12 · F2-05: 79 variables (6 colecciones) + 20 text styles ligados en Figma; mapping a tokens.css documentado · Siguiente: F2-06
- 2026-11-12 · F2-06: 80 variantes de componentes aprobadas (foco de inputs 2 px); F2 cerrado · Siguiente: F3-01
- 2026-11-12 · F3-01: Home hi-fi armado (instancias + fotos reales); hero D2 aprobado (banda tras el edificio, recorte auto-segmentado) · Siguiente: aprobación completa de F3-01 → F3-02
- 2026-11-12 · F3-01 aprobado; logo OPUS en Nav/Footer; F3-02 Projects hi-fi (All + filtro Housing) con categorías reales de OPUS · Siguiente: aprobación F3-02

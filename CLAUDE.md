# CLAUDE.md — OPUS · Brutalist Web Redesign (unsolicited concept)

> Este archivo se carga en cada sesión. Es la fuente de verdad del proyecto.
> Si algo aquí entra en conflicto con una instrucción puntual de Santiago, **pregunta** antes de actuar.

---

## 0. Reglas de oro (leer siempre)

1. **Pregunta antes de ejecutar.** Si hay ambigüedad, falta información o hay más de un camino razonable, haz las preguntas **antes** de empezar. Agrúpalas (máx. 5 por tanda), numeradas.
2. **Nunca saltes una compuerta (gate)** del flujo de diseño sin un "aprobado" explícito de Santiago (ver §4).
3. **Siempre da opciones** (mínimo 3 en low-fi y en sistema de diseño), cada una con su razonamiento de UX **y** de conversión, y cierra con tu recomendación.
4. **Señala toda tensión entre brutalismo y conversión** con el formato de §5.3. Nunca la resuelvas en silencio.
5. **Cero atribución a Claude en Git/GitHub** (ver §9). Es una regla explícita del dueño del repo.
6. **No inventes datos de OPUS.** Proyectos, premios, cifras, nombres y textos salen de fuentes públicas de OPUS. Lo que no esté verificado se marca `[VERIFY]`.
7. **Ahorra tokens:** respuestas concisas, lee solo los archivos necesarios, no vuelvas a escanear las referencias si ya existe `docs/references.md` (§7).
8. **Idiomas:** habla con Santiago en **español**. Todo el contenido de la web, el código, los commits, los nombres de variables/tokens y el README van en **inglés**.

---

## 1. Contexto del proyecto

- **Qué es:** rediseño completo, **no solicitado** (unsolicited redesign), de la web de **OPUS**, oficina de diseño, arquitectura y paisaje de Medellín, Colombia (fundada en 2006 y liderada por Carlos Betancur, Manuel Jaén y Carlos Montoya). Web actual: http://opusestudio.com (Santiago ya la auditó; pídele sus hallazgos antes de auditarla tú).
- **Estética:** brutalismo web. Mostrar solo lo necesario, y que eso necesario *grite*: jerarquía radical, tipografía protagonista, crudeza honesta, nada de decoración superflua.
- **Objetivos (en orden):**
  1. Pieza de **portafolio** + repo público en GitHub con un caso de estudio sólido.
  2. Probar el modelo **Fable** en un proyecto real de punta a punta.
  3. Opcional y no urgente: si surge la oportunidad, ofrecérselo a OPUS.
- **Conversión principal:** `Book a consultation`: el usuario agenda una cita para hablar de un proyecto arquitectónico, paisajístico o de diseño.
- **Alcance técnico:** front con animaciones (parallax, transiciones con scroll) + back con **panel de admin de citas**, desplegado en **Vercel**.
- **Repo:** https://github.com/SantiagoJmillora/BRUTALISM_WEB_DESIGN (público).
- **Carpeta local del código:** `C:\dev\Proyecto brutalista` (fuera de OneDrive a propósito).
- **Dedicación:** indefinida; sesiones cuando Santiago pueda. Cada sesión debe dejar el proyecto en un estado retomable.

---

## 2. Roles de Claude (simultáneos)

| Rol | Responsabilidad | Pregunta que siempre se hace |
|---|---|---|
| **Diseñador web senior UI/UX** | Arquitectura de información, jerarquía, usabilidad, accesibilidad, sistema de diseño, motion | ¿Se entiende en 3 segundos en un móvil? |
| **Experto en ventas / CRO** | Embudo, CTAs, fricción, prueba social, copy persuasivo | ¿Esto acerca o aleja al usuario de agendar la cita? |
| **Ingeniero full-stack** | Código limpio, tipado, seguro, rápido, testeado | ¿Esto es mantenible y lo puedo defender en una entrevista? |

Cada propuesta de diseño incluye una línea de **UX** y una de **Conversión**.

---

## 3. Recursos

### 3.1 Figma
- **Archivo:** https://www.figma.com/design/UFF7zUSZmyhzJpxi3ZLM1s/TEST?node-id=2031-65 (renombrado "Campo de prueba"). Páginas: `01 Foundations` (referencias, design system y `Archive · …` con lo descartado) · `02 Mobile` (solo lo aprobado) · `03 Desktop`.
- **Plan gratuito → máximo 3 páginas.** La primera tarea de diseño es proponer cómo organizar todo (referencias, low-fi, sistema de diseño, hi-fi, prototipo) dentro de 3 páginas, usando secciones y frames con nombres claros. Dar opciones y esperar aprobación.
- **Acceso:** preferir el **navegador** (Claude in Chrome, sesión iniciada por Santiago) para no gastar llamadas del conector de Figma. Usar el MCP de Figma solo si Santiago lo aprueba para una tarea concreta, y agrupar las llamadas.
- **Nunca** pedir ni escribir contraseñas. Si hace falta iniciar sesión, Santiago lo hace.
- Las opciones descartadas **no se borran**: quedan en Figma como registro del proceso (sirven para el caso de estudio).
- Frames base: **mobile 390 × 844** (diseñar aquí primero); desktop **1440 × 900** (después).

### 3.2 Referencias (en el PC, dentro del repo, ignoradas por git)
- `C:\dev\Proyecto brutalista\Referencias\Referencias ESTRUCTURALES` — fotos de OPUS seleccionadas por Santiago (`OPUS REF #1–#17`, webp). Hero del Home: #1, #7, #8, #9.
- `C:\dev\Proyecto brutalista\Referencias\Referencias WEB`
- Imágenes de proyectos descargadas de opusestudio.com: `C:\dev\Proyecto brutalista\assets-src\opus-projects\` (gitignored, con `manifest.json` de fuentes y créditos).
- Estas carpetas no se sincronizan entre PCs: en el otro PC hay que copiarlas (o volver a correr la descarga).
- La antigua carpeta de OneDrive (`C:\Users\zyroc\OneDrive\Escritorio\Proyecto brutalista\Referencias`) solo tiene imágenes de mood de Pinterest ya resumidas en `docs/references.md`; no se usa.
- Analízalas **una sola vez** y resume en `docs/references.md` (ver §7).

### 3.3 Contenido e imágenes
- Textos y datos de proyectos: de fuentes públicas de OPUS (web, ArchDaily, prensa). Registra la fuente en `docs/content-sources.md`.
- Imágenes: Santiago las trae de Pinterest u otras fuentes. **Siempre** registra en `docs/assets-credits.md` el origen y el fotógrafo si se conoce.
- Si algún día se le vende a OPUS, todas las imágenes deben reemplazarse por material de OPUS (está en el backlog).

---

## 4. Flujo de trabajo de diseño (con compuertas)

```
Discovery → Low-fi (opciones) → ✅ → Design system (opciones) → ✅ → Hi-fi → ✅ → Prototipo → ✅ → Código
           └──────────────── MOBILE primero ────────────────┘  luego se repite el ciclo para DESKTOP
```

- **Mobile first, siempre.** Desktop se diseña cuando el mobile de esa vista ya está aprobado en hi-fi.
- **Low-fi:** mínimo 3 opciones por vista o flujo clave, en escala de grises, sin tipografía final. Por cada opción: idea en una línea, pros y contras de UX, impacto en conversión. Cierra con tu recomendación.
- **Design system:** mínimo 3 opciones para cada eje (tipografía, color, grid/espaciado, motion). Ver §6.
- **Hi-fi:** aplica el sistema aprobado. Sin valores sueltos: todo sale de tokens.
- **Prototipo:** en Figma; flujo principal (home → proyecto → booking → confirmación) + specs de motion.
- **Compuerta = esperar el "aprobado" de Santiago.** Si responde con cambios, itera y vuelve a pedir aprobación.
- Al cerrar cada compuerta, registra la decisión en `docs/DECISIONS.md` (§10).

---

## 5. Principios de diseño y conversión

### 5.1 Brutalismo con intención
- Lo necesario grita: un mensaje y un CTA dominante por pantalla.
- Tipografía como estructura; grid visible o sugerido; contraste extremo.
- Crudeza con propósito, nunca por descuido: alineaciones exactas, ritmo consistente.
- Las fotos de los proyectos de OPUS son la prueba del valor del estudio: tratarlas como protagonistas.

### 5.2 Conversión
- CTA primario único: **"Book a consultation"**, visible en cada vista. En mobile, CTA fijo (sticky) que no tape contenido clave.
- Booking en **≤ 3 pasos** y mínimo de campos (nombre, email, tipo de proyecto, mensaje corto, horario).
- Prueba social real (premios y proyectos verificados, p. ej. la Albarrada de Mompox, ganadora de la BLAP) cerca de los CTAs.
- Velocidad = conversión: ver los presupuestos de rendimiento en §8.4.
- Microcopy claro y en inglés directo; nada de jerga vacía.

### 5.3 Protocolo de tensión (obligatorio)
Cuando una decisión estética perjudique la usabilidad, la accesibilidad o la conversión:

```
⚠️ TENSIÓN brutalismo vs conversión
Problema: <qué se rompe y para quién>
Opción A: <más brutal> — costo: <...>
Opción B: <más convertible> — costo: <...>
Opción C: <punto medio> — costo: <...>
Recomendación: <cuál y por qué>
```
Espera la decisión de Santiago.

### 5.4 Accesibilidad (no negociable)
- WCAG 2.2 **AA**: contraste mínimo 4.5:1 en texto normal y 3:1 en texto grande o UI.
- Navegable por teclado, foco visible y con estilo brutalista (no quitar el outline sin reemplazo).
- `prefers-reduced-motion`: desactiva parallax y transiciones grandes.
- Targets táctiles de al menos 44 × 44 px.
- HTML semántico y `alt` descriptivo en todas las imágenes de proyectos.

---

## 6. Sistema de diseño y tokens

### 6.1 Qué entregar como opciones
- **Tipografía:** 3 combinaciones (display + texto), con licencia libre para web (Google Fonts, Fontshare u otra fuente con licencia clara). Escala tipográfica fluida para mobile y desktop.
- **Color:** 3 paletas con contraste verificado (adjuntar ratios). Brutalismo ≠ solo blanco y negro: incluir al menos una opción con color de acento.
- **Grid y espaciado:** 3 propuestas (columnas, gutters, márgenes) y una escala de espaciado (p. ej. base 4 u 8).
- **Motion:** 3 lenguajes de movimiento (duraciones, easings, tipos de transición), coherentes con el brutalismo.

### 6.2 Tokens: una sola fuente de verdad
Un **token** es un valor del sistema con nombre (color, tamaño, espacio, radio, duración). Se define **una vez** y se usa igual en Figma y en código:

| Figma (Variables / Styles) | Código (CSS custom properties) |
|---|---|
| `color/ink` | `--color-ink` |
| `color/paper` | `--color-paper` |
| `space/4` | `--space-4` |
| `font/size/display-xl` | `--font-size-display-xl` |
| `motion/duration/fast` | `--motion-duration-fast` |

- Nombres en inglés, en kebab-case en código y con `/` en Figma.
- Fuente de verdad en código: `src/styles/tokens.css`, expuesta a Tailwind con `@theme`.
- Si el plan gratuito de Figma limita las Variables, usar Styles y documentar los tokens en `docs/design-system.md`.
- **Prohibido** usar valores sueltos (hex, px) en componentes; si falta un token, se propone y se agrega.

---

## 7. Economía de tokens (para usar Fable con eficiencia)

- `docs/references.md`: resumen único de las referencias (patrones, tipografías, layouts, motion, qué tomar y qué evitar). Una vez creado, **no se vuelven a leer las imágenes** salvo que Santiago lo pida.
- Lee solo los archivos que la tarea necesita; nada de exploraciones amplias del repo sin motivo.
- Respuestas cortas: lo que se hizo, lo que sigue y las preguntas. Sin repetir contexto que ya está en este archivo.
- Antes de instalar o usar una librería, **verifica la versión estable actual y su API en la documentación oficial**; no asumas APIs de memoria.

---

## 8. Stack técnico

### 8.1 Decisión (y por qué)
| Capa | Elección | Motivo |
|---|---|---|
| Framework | **Next.js (App Router) + TypeScript (strict)** | Front, API, auth y admin en un solo repo; nativo en Vercel; muy valorado en portafolios |
| Estilos | **Tailwind CSS v4** + `tokens.css` | `@theme` sobre variables CSS = tokens sincronizados con Figma |
| Animación | **GSAP + ScrollTrigger** | Estándar para parallax y animaciones atadas al scroll |
| Smooth scroll | **Lenis** | Se integra con ScrollTrigger; desactivable con reduced-motion |
| Base de datos | **Postgres en Neon** (vía Vercel Marketplace) | Serverless, plan gratuito, integración directa |
| ORM | **Drizzle ORM** + drizzle-kit | Tipado fuerte, migraciones en SQL legible |
| Auth (admin) | **Better Auth** (email + contraseña, un solo admin) | Simple, moderno, sin vendor lock-in |
| Email | **Resend** (+ React Email) | Confirmaciones de cita y aviso al admin |
| Validación | **Zod** | Mismo esquema en cliente y servidor |
| Fechas | **date-fns** + `@date-fns/tz` | Guardar en UTC, mostrar en `America/Bogota` |
| Tests | **Vitest** (unit) + **Playwright** (e2e) | Lógica de booking y flujos críticos |
| Calidad | ESLint + Prettier + `tsc --noEmit` | Antes de cada commit |
| Paquetes | **pnpm** (vía corepack) | Rápido, lockfile estricto |
| Deploy | **Vercel** (preview por rama, producción desde `main`) | — |

Si Fable encuentra una razón técnica fuerte para cambiar algo de esta tabla, la propone con pros y contras y **espera aprobación**.

### 8.2 Motion en la práctica
- Animar solo `transform` y `opacity`. Nada de animar `top`, `left`, `width` ni `height`.
- Parallax moderado en mobile (o desactivado si afecta el rendimiento); nunca secuestrar el scroll nativo de iOS.
- Los componentes animados se limpian al desmontar (`gsap.context()` + `revert()`).
- `prefers-reduced-motion: reduce` → sin parallax ni Lenis; transiciones instantáneas o fades cortos.

### 8.3 Back: MVP del panel de admin
- **Un solo admin** (Santiago) con login. Sin registro público.
- El admin define la **disponibilidad** (horarios); el usuario reserva **un** horario libre.
- Al reservar: email de confirmación al usuario y aviso al admin.
- En el panel, el admin ve, **confirma** o **cancela** las citas (estados: `pending` → `confirmed` | `cancelled`).
- Evitar dobles reservas con una restricción única en la base de datos sobre el horario, no solo con validación en el cliente.
- Anti-spam: honeypot + rate limiting en la acción de reserva.
- Todas las mutaciones pasan por Server Actions o Route Handlers con validación Zod y verificación de sesión en el servidor.
- Futuro (no MVP): sincronizar con Google Calendar.
- Nota: Resend sin dominio verificado solo envía al email de la cuenta, lo cual sirve para la demo.

### 8.4 Presupuestos de calidad
- Lighthouse mobile: Performance ≥ 90, Accessibility ≥ 95, Best Practices ≥ 95, SEO ≥ 90.
- LCP < 2.5 s, CLS < 0.1, INP < 200 ms.
- Imágenes con `next/image`, formatos modernos y `sizes` correctos. Fuentes con `next/font`.

### 8.5 Estructura sugerida
```
/
├─ CLAUDE.md
├─ BACKLOG.md
├─ README.md               # incluye disclaimer, stack, screenshots, link al caso de estudio
├─ docs/
│  ├─ DECISIONS.md          # log de decisiones (§10)
│  ├─ references.md         # resumen único de referencias
│  ├─ design-system.md      # tokens y reglas
│  ├─ content-sources.md    # de dónde sale cada dato de OPUS
│  ├─ assets-credits.md     # origen y crédito de cada imagen
│  └─ case-study.md         # se construye durante el proyecto
├─ src/
│  ├─ app/                  # rutas (públicas + /admin)
│  ├─ components/           # ui/, sections/, motion/
│  ├─ lib/                  # db/, auth/, email/, validation/, booking/
│  └─ styles/tokens.css
├─ drizzle/                 # migraciones
├─ tests/                   # unit/ y e2e/
└─ .env.example             # nunca .env real
```

---

## 9. Git y GitHub

### 9.1 Atribución: PROHIBIDA
- **Nunca** agregar `Co-Authored-By: Claude...` ni ninguna línea de co-autoría de Claude o Anthropic en commits.
- **Nunca** agregar "Generated with Claude Code" ni enlaces similares en commits, PRs, issues o README.
- Claude **no** figura como colaborador ni como autor. El autor de cada commit es la identidad git de Santiago; **no modificar `git config`**.
- Refuerzo técnico: `.claude/settings.json` desactiva la atribución automática. No tocar ese archivo.

### 9.2 Convenciones
- **Conventional Commits** en inglés: `feat:`, `fix:`, `style:`, `refactor:`, `docs:`, `test:`, `chore:`, `perf:`. Ej.: `feat(booking): add slot availability check`.
- Ramas: `main` siempre desplegable. Trabajo en `feat/<id-backlog>-<slug>`, `fix/...`, `docs/...`, `chore/...`.
- Commits pequeños y atómicos. Antes de commitear: lint + typecheck + tests relevantes en verde.
- Haz el commit al cerrar cada tarea del backlog y muestra el mensaje. **Push y merge a `main` solo con OK de Santiago.**
- Nunca `push --force` a `main`. Nunca commitear `.env*` (excepto `.env.example`), secretos ni `node_modules`.

### 9.3 Dos PCs (Windows 10 y Windows 11)
- **Inicio de sesión:** `git pull`. **Fin de sesión:** commit + push (con OK).
- `.gitattributes` con `* text=auto eol=lf` para evitar conflictos de fin de línea.
- Fijar la versión de Node LTS en `.nvmrc` y en `engines`; usar pnpm vía corepack en ambos PCs.
- Las variables de entorno se configuran en cada PC (`.env.local`) y en Vercel; documentar las necesarias en `.env.example`.

---

## 10. Documentación para el portafolio

- `docs/DECISIONS.md`: una entrada por decisión relevante, con este formato:
  ```
  ## YYYY-MM-DD — <decisión>
  Contexto: ... | Opciones: A, B, C | Elegida: B | Por qué: ... | Tensión: sí/no
  ```
- `docs/case-study.md`: se alimenta al cerrar cada fase (problema, proceso, opciones descartadas, resultado, métricas de Lighthouse, aprendizajes, y experiencia usando Fable).
- Capturas de cada fase en `docs/img/` (low-fi, hi-fi, final).

---

## 11. Ética y legal (unsolicited redesign)

- Footer de la web y README: **"Unofficial concept redesign. Not affiliated with or endorsed by OPUS."**
- Meta `robots: noindex` en producción, para no competir en buscadores con la web oficial ni parecer ser ella.
- El flujo de booking muestra un aviso visible: **"Concept project — bookings are not sent to OPUS."** Si esto choca con la conversión, aplicar §5.3, pero el aviso no se elimina.
- **No** usar emails, teléfonos ni formularios reales de OPUS. Las notificaciones llegan solo a Santiago.
- Créditos de fotógrafos y fuentes en `docs/assets-credits.md` y en un crédito visible cuando aplique.

---

## 12. Ritual de sesión

**Al iniciar:**
1. `git pull` y revisar `git status`.
2. Leer `BACKLOG.md` (solo la fase activa y la sección *Now*).
3. Resumir en 3 líneas dónde quedamos y proponer la tarea siguiente. Preguntar si es esa u otra.

**Durante:** una tarea `[~]` a la vez. Si aparece trabajo nuevo, va a *Inbox* del backlog; no se desvía la sesión.

**Al cerrar:**
1. Actualizar `BACKLOG.md` (estados y una línea en el *Session log*).
2. Registrar decisiones en `docs/DECISIONS.md`.
3. Commit (y push con OK).
4. Dejar escrito en *Now* cuál es el siguiente paso exacto.

---

## 13. Definition of Done (por tarea)

- [ ] Cumple los criterios de aceptación del backlog.
- [ ] Diseño: aprobado por Santiago en Figma (si aplica).
- [ ] Código: lint + typecheck + tests en verde; sin valores sueltos fuera de tokens.
- [ ] Accesible (AA) y respeta reduced-motion (si aplica).
- [ ] Probado en un viewport de 390 px y, cuando corresponda, en 1440 px.
- [ ] Backlog y DECISIONS actualizados; commit hecho sin atribución a Claude.

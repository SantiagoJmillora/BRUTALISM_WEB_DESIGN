# Decision log

> One entry per relevant decision. Newest at the top.
>
> Format:
>
> ```
> ## YYYY-MM-DD — <decision>
> Contexto: ... | Opciones: A, B, C | Elegida: B | Por qué: ... | Tensión: sí/no
> ```

## 2026-11-12 — Home low-fi mobile: Monolith (F1-03)
Contexto: 3 conceptos de Home a 390 px. | Opciones: A) Monolith (foto primero, un proyecto por pantalla), B) Index (tipografía primero), C) Chapters (bloques de color + carrusel) | Elegida: A | Por qué: fotos protagonistas, tipografía delante/detrás del edificio (mandato), CTA sticky + prueba social tras el hero. Detalle en `docs/lowfi.md`. | Tensión: sí — contraste del texto sobre foto → C: tratamiento monocromo/oscurecido bajo el texto + CTA sticky desde el primer render.

## 2026-11-12 — Booking and admin flows (F1-02)
Contexto: flujo de reserva ≤ 3 pasos y panel de un solo admin, mobile-first. | Opciones booking: A) proyecto primero, B) hora primero, C) página única progresiva · admin: A) lista, B) calendario, C) bandeja + agenda | Elegidas: booking A, admin C; + emails de confirmación y cancelación al usuario; consulta de 30 min | Por qué: A = compromiso progresivo, prefill desde proyecto, métricas por paso, más accesible; C = lo que requiere acción primero, legible en 390 px, slots en bloque, esfuerzo bajo. Detalle en `docs/user-flows.md`. | Tensión: no

## 2026-11-12 — Information architecture: hybrid (F1-01)
Contexto: sitemap mobile-first con 26 proyectos (8 destacados). | Opciones: A) one-page narrativa, B) multipágina clásica, C) híbrida | Elegida: C | Por qué: Home narrativa con prueba social a un scroll del CTA; nav de 3 ítems (Projects · Studio · Book); 8 detalles completos + 18 ligeros en un archivo filtrable; `/book` dedicado con prefill desde proyecto. Detalle en `docs/information-architecture.md`. | Tensión: no

## 2026-11-12 — Featured projects (F0-08) and home hero photos
Contexto: 6–8 proyectos destacados que cubran los segmentos de la estrategia; fotos del hero. | Opciones: los 6 de Santiago + 1–2 de Claude (Mompox, Tatamá, Oviedo) | Elegida: Plaza de la Libertad, MOVA, Casa La Pausa, Forum UdeM, Auditorio La Enseñanza, CEFE Las Cometas + Albarrada de Mompox + Hospital Tatamá. Hero: OPUS REF #1, #7, #8, #9 (fotos reales de OPUS; reemplazan las de Pinterest E1–E5). | Por qué: Mompox sostiene la propuesta "architecture and landscape" (BLAP); Tatamá respalda el premio WAF 2024 de la franja de prueba social. | Tensión: no

## 2026-11-12 — OPUS project images: originals local, optimized selection committed
Contexto: 545 imágenes (26 proyectos) descargadas de opusestudio.com para las páginas de proyecto; son © de OPUS y de sus fotógrafos y el repo es público. | Opciones: A) commitearlas al repo público, B) mantenerlas fuera de git (`assets-src/`, gitignored) hasta decidir, C) publicarlas solo en el deploy vía almacenamiento externo | Elegida: B para los originales (233 MB, demasiado peso para git) + Santiago aprueba publicar en el repo **solo las imágenes que se usen**, optimizadas (WebP, ancho máx. ~2000 px), con crédito visible y en assets-credits. | Por qué: Santiago quiere las fotos en el repo; meter 545 originales infla el historial de git para siempre, la selección optimizada no. | Tensión: no

## 2026-11-12 — Conversion strategy (F0-07)
Contexto: definir públicos, propuesta de valor y embudo. | Opciones: booking para todos los segmentos vs. solo privados/desarrolladores | Elegida: booking diseñado para privados + desarrolladores (instituciones caben); el sector público se atiende con prueba social, no con el formulario. Propuesta: "Architecture and landscape, designed as one." Detalle en `docs/conversion-strategy.md`. | Tensión: sí — ambas resueltas con C: aviso de concepto dentro del booking (paso 1 + confirmación) + footer; hero con tipografía gigante sobre foto + CTA sticky + franja de premios justo después.

## 2026-11-12 — Figma structure in 3 pages, by platform (F0-04)
Contexto: plan gratuito = máx. 3 páginas; mobile primero, luego desktop; descartes se conservan. | Opciones: A) Por fase: `01 Discovery & Low-fi` · `02 Design System` · `03 Hi-fi & Prototype`; B) Por plataforma: `01 Foundations` (refs + design system) · `02 Mobile` (low-fi→hi-fi→proto en filas) · `03 Desktop`; C) Por estado: `01 Process / Archive` (refs, low-fi, descartes) · `02 System` · `03 Final` (hi-fi aprobado + prototipo, mobile y desktop) | Elegida: B | Por qué: sigue el orden mobile-first; cada vista es una fila (low-fi → discarded → hi-fi → prototype) que cuenta su evolución completa para el caso de estudio; el prototipo vive en la misma página que sus pantallas; ninguna página se satura. | Tensión: no

## 2026-11-12 — Node version pinned to 24 (LTS)
Contexto: `.nvmrc` para dos PCs y Vercel. Node 26 es el LTS activo desde oct 2026, pero este PC tiene 24.16.0 instalado y Node 24 sigue siendo LTS soportado. | Opciones: A) 24, B) 26 | Elegida: A | Por qué: coincide con lo instalado, soportado por Vercel; migrar a 26 queda en backlog si hace falta. | Tensión: no

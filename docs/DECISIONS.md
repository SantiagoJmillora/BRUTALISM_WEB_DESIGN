# Decision log

> One entry per relevant decision. Newest at the top.
>
> Format:
>
> ```
> ## YYYY-MM-DD — <decision>
> Contexto: ... | Opciones: A, B, C | Elegida: B | Por qué: ... | Tensión: sí/no
> ```

## 2026-11-12 — Home hi-fi approved (F3-01) · OPUS logo in Nav and Footer components
Contexto: cierre del hi-fi del Home; Santiago aporta el logotipo de OPUS. | Elegida: Home hi-fi aprobado (hero D2 + franja de premios + 8 destacados + disciplinas + Studio + footer). Logo (raster, tintado papel/tinta) dentro del componente Nav (4 variantes, 34 px) y del Footer (56 px) → se propaga a todas las vistas. | Pendiente: SVG del logo para F6; decidir si el "OPUS" tipográfico gigante del hero convive con el logo. | Tensión: no

## 2026-11-12 — Home hero: ink band behind the building, OPUS on top (F3-01)
Contexto: en el hero hi-fi la palabra "OPUS" (papel) se perdía en el cielo gris de REF #1. | Opciones: A) delineado negro, B) letras en tinta, C) overlay superior, D) banda de tinta detrás del texto, E) blend "difference" | Elegida: D2 (variante de D propuesta por Santiago, con ajustes suyos en Figma): capas foto → banda de tinta → edificio recortado → overlay → OPUS. Parallax P1: foto + recorte 0.7×, banda + OPUS 0.45× (la banda se esconde tras la torre). Nav del hero con fondo de tinta (texto papel sobre cielo claro no era legible). | Por qué: contraste garantizado sobre el cielo y la tipografía "interactúa" con el edificio (mandato de letras delante/detrás). "OPUS" es logotipo (exento de contraste WCAG) y va aria-hidden. Recorte auto-segmentado (cielo = liso + claro, flood fill desde el borde superior); en F6 se exporta WebP con alfa ≤ 150 KB @ 1200 px. Regla: la foto del hero debe tener cielo segmentable. | Tensión: no

## 2026-11-12 — Base components approved; input focus 2 px (F2-06) · Design system closed (F2)
Contexto: 80 variantes de componentes sobre variables. | Cambio de Santiago: el foco de inputs pasa de borde 3 px + aro a **borde de tinta 2 px sin aro** (menos aparatoso). Botones, chips, links y slots mantienen el aro (2 px papel + 3 px tinta). | Por qué: el foco de campos se veía pesado. Cumple WCAG 2.2 AA (2.4.7 foco visible); si en pruebas el cambio 1→2 px se percibe poco, opción: borde por defecto en `muted`. | Tensión: no

## 2026-11-12 — Tokens in Figma Variables, responsive split in two collections (F2-05)
Contexto: el plan gratuito de Figma permite Variables pero solo 1 modo por colección. | Opciones: A) Styles + documentación, B) Variables con colecciones Mobile/Desktop de nombres idénticos, C) un solo set con sufijos -mobile/-desktop | Elegida: B (79 variables en 6 colecciones + 20 text styles con tamaño ligado a variables) | Por qué: mantiene los nombres de §6.2 sin sufijos; en código ambas colapsan en un token fluido con clamp(). | Tensión: no

## 2026-11-12 — Motion: Mechanical / hard cuts (F2-04)
Contexto: lenguaje de movimiento coherente con brutalismo y rendimiento. | Opciones: A) mecánico (100/200/400/700 ms, cortes secos), B) masa pesada (200–1400 ms), C) editorial calmo (fades) | Elegida: A | Por qué: el parallax P1+P2 ya da el momento cinematográfico; el resto debe sentirse instantáneo (INP percibido, CTA responde al instante). Reglas de reduced-motion en `docs/design-system.md`. | Tensión: no

## 2026-11-12 — Grid & spacing: Swiss 4/12, base 4 (F2-03)
Contexto: grid mobile/desktop y escala de espaciado. | Opciones: A) suizo 4/12 base 4, B) modular denso 6/12 base 8 con grid visible, C) editorial asimétrico 4/16 + línea base 8 | Elegida: A (mobile 4 col · margen 16 · gutter 16; desktop 12 col · margen 48 · gutter 24; space/N = N×4 px; sección clamp 64→160) | Por qué: coincide con el low-fi aprobado (cero retrabajo), 12 columnas dan 8/4 limpios. Líneas de columna de B solo como ornamento puntual. | Tensión: no

## 2026-11-12 — Color: Concrete + Signal Orange #FF5B14 (F2-02)
Contexto: paleta con contraste AA verificado y un acento. | Opciones: A) concreto + naranja señal, B) monocromo estricto, C) tinta + verde ácido | Elegida: A con acento cambiado por Santiago a `#FF5B14` (más eléctrico) | Por qué: el CTA es lo único naranja en pantalla; paleta cálida "de obra", no tech. Reglas: CTA con borde de tinta 2 px sobre fondos claros (naranja/papel 2.7:1); texto del CTA siempre en tinta (6.1:1; blanco solo 3.1:1); errores con ícono + texto; overlay de fotos = tinta 65%. | Tensión: no

## 2026-11-12 — Typography: Barlow Condensed + Barlow + IBM Plex Mono (F2-01)
Contexto: tipografía display + texto + mono para datos, licencia libre web, escala fluida 390→1440. | Opciones: A) Barlow Condensed + Barlow + IBM Plex Mono, B) Anton + Inter + JetBrains Mono, C) Big Shoulders Display + Public Sans + Space Mono | Elegida: A | Por qué: superfamilia coherente con voz cívica/infraestructura; condensada cabe nombres largos a 390 px; cuerpo muy legible para formularios. Costo: Barlow es estática (~5 archivos woff2). Escala de 9 tokens en `docs/design-system.md`. | Tensión: no

## 2026-11-12 — Low-fi MOBILE closed (F1-09)
Contexto: cierre de la fase F1. | Elegidas: IA C (híbrida) · Flujos booking A + admin C · Home A (Monolith) + parallax 2 (P1+P2, mobile y desktop) · Projects A · Detail B2 + B-LIGHT · Studio C2 · Booking A · Admin A (+ repetir 4 semanas) | Descartadas: IA A/B · booking B/C · admin-flow A/B · Home B/C · parallax P3/P4 y combinaciones 1/3 · Projects B/C · Detail A/B/C/A-LIGHT · Studio A/B/C · Booking B/C · Admin B/C. | Figma: aprobadas en `02 Mobile` (una sección por vista, compactada); descartadas movidas a `01 Foundations` (secciones "Archive · …"), no borradas. Detalle en `docs/lowfi.md`. | Tensión: resueltas en sus entradas (hero, detalle, studio).

## 2026-11-12 — Admin low-fi: sections + detail + bottom tabs (F1-08)
Contexto: panel de un solo admin en 390 px, flujo C (bandeja + agenda). | Opciones: A) secciones + detalle + tabs, B) tabs + acciones en tarjeta + grilla semanal, C) swipe | Elegida: A + "repetir el mismo día 4 semanas" al crear slots en bloque (añadido de alcance aprobado) | Por qué: menor riesgo (toda acción destructiva confirmada con consecuencias), legible en móvil, testeable. | Tensión: no

## 2026-11-12 — Booking low-fi: full-page steps + fixed bottom bar (F1-07)
Contexto: presentación visual del flujo A (proyecto → hora → datos) y sus estados. | Opciones: A) pasos a pantalla completa + barra fija, B) conversacional 7 pantallas, C) rail de resumen | Elegida: A + estado "sin horarios" = saltar a la próxima fecha disponible (o mensaje honesto + link a Projects; sin captura de email) | Por qué: foco, acciones en zona del pulgar, progreso 1/3 claro, todos los estados cubiertos. | Tensión: no

## 2026-11-12 — Studio: manifesto + 20-year timeline (F1-06)
Contexto: página de credibilidad para instituciones/sector público y cara humana del estudio. | Opciones: A) dossier, B) manifiesto + personas, C) línea de tiempo | Elegida: C2 = primera pantalla de B (manifiesto) + C (timeline 2006→2025 con hitos verificados), socios/equipo/clientes como listas de texto | Por qué: Santiago quiere contar los 20 años de trayectoria tras un arranque contundente. | Tensión: sí — premios recientes al final → C: franja "Latest recognition" tras el manifiesto.

## 2026-11-12 — Project detail: short editorial B2 + B-LIGHT (F1-05)
Contexto: plantilla de detalle para 8 destacados y 18 de archivo. | Opciones: A) ficha primero, B) historia editorial, C) galería inmersiva | Elegida: B revisada por Santiago → B2 (hero → quote + intro corta → galería protagonista → acordeón de datos → CTA) + B-LIGHT | Por qué: las fotos son lo que más le interesa al cliente; sin textos largos inventados. | Tensión: sí — prueba enterrada en el acordeón → C: franja de 3 datos (ubicación · estado · premio) bajo el hero.

## 2026-11-12 — Projects index low-fi: showcase + archive table (F1-04)
Contexto: listado de 26 proyectos (8 destacados + 18 archivo) en 390 px. | Opciones: A) destacados grandes + tabla de archivo, B) índice numerado único, C) mosaico | Elegida: A | Por qué: materializa la IA híbrida; filtros con las 5 categorías de OPUS en `?type=` (alimenta el prefill del booking); estado vacío con CTA. | Tensión: no

## 2026-11-12 — Home parallax: hero depth + inner image (F1-03b)
Contexto: Santiago pidió parallax claro en el low-fi de Home A. | Opciones: 1) Sutil (P2), 2) Hero con profundidad (P1+P2), 3) Coreografía completa (P1–P4) | Elegida: 2 para mobile **y desktop** | Por qué: un solo momento "wow" (letras que se hunden detrás del edificio) y calma después; protege el CTA y el rendimiento. Desktop no escala a la 3 por decisión de Santiago. | Tensión: no

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

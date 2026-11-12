# Decision log

> One entry per relevant decision. Newest at the top.
>
> Format:
>
> ```
> ## YYYY-MM-DD — <decision>
> Contexto: ... | Opciones: A, B, C | Elegida: B | Por qué: ... | Tensión: sí/no
> ```

## 2026-11-12 — Figma structure in 3 pages, by platform (F0-04)
Contexto: plan gratuito = máx. 3 páginas; mobile primero, luego desktop; descartes se conservan. | Opciones: A) Por fase: `01 Discovery & Low-fi` · `02 Design System` · `03 Hi-fi & Prototype`; B) Por plataforma: `01 Foundations` (refs + design system) · `02 Mobile` (low-fi→hi-fi→proto en filas) · `03 Desktop`; C) Por estado: `01 Process / Archive` (refs, low-fi, descartes) · `02 System` · `03 Final` (hi-fi aprobado + prototipo, mobile y desktop) | Elegida: B | Por qué: sigue el orden mobile-first; cada vista es una fila (low-fi → discarded → hi-fi → prototype) que cuenta su evolución completa para el caso de estudio; el prototipo vive en la misma página que sus pantallas; ninguna página se satura. | Tensión: no

## 2026-11-12 — Node version pinned to 24 (LTS)
Contexto: `.nvmrc` para dos PCs y Vercel. Node 26 es el LTS activo desde oct 2026, pero este PC tiene 24.16.0 instalado y Node 24 sigue siendo LTS soportado. | Opciones: A) 24, B) 26 | Elegida: A | Por qué: coincide con lo instalado, soportado por Vercel; migrar a 26 queda en backlog si hace falta. | Tensión: no

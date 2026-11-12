# Decision log

> One entry per relevant decision. Newest at the top.
>
> Format:
>
> ```
> ## YYYY-MM-DD — <decision>
> Contexto: ... | Opciones: A, B, C | Elegida: B | Por qué: ... | Tensión: sí/no
> ```

## 2026-11-12 — Node version pinned to 24 (LTS)
Contexto: `.nvmrc` para dos PCs y Vercel. Node 26 es el LTS activo desde oct 2026, pero este PC tiene 24.16.0 instalado y Node 24 sigue siendo LTS soportado. | Opciones: A) 24, B) 26 | Elegida: A | Por qué: coincide con lo instalado, soportado por Vercel; migrar a 26 queda en backlog si hace falta. | Tensión: no

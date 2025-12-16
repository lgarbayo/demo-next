# Next.js App Router — Dashboard Demo (Next.js Learn)

Demo full-stack construida siguiendo el **curso oficial "Dashboard App" (App Router)** de Next.js Learn.
La intención es **usar esta app como demo técnica** en una exposición (10–15 min) para explicar *qué aporta Next.js* más allá de React.

> Esta demo está centrada en el **App Router** (arquitectura moderna recomendada) y en features como Server Components, Streaming, Server Actions, manejo de errores, autenticación y metadata. :contentReference[oaicite:1]{index=1}

---

## Qué enseña esta demo (en serio)

Esta aplicación no está pensada como “producto final”, sino como un **recorrido por decisiones de arquitectura**:

- **Routing por filesystem** con `app/` (sin React Router)
- **Layouts anidados y persistentes** (UI estable entre rutas)
- **Server Components** por defecto (menos JS al cliente)
- **Data fetching en servidor** y patrón de componentes para datos
- **Rendering estático vs dinámico** (caching + revalidación)
- **Streaming** con `loading.tsx` (mejor UX en cargas)
- **Search & Pagination** usando **URL search params** (estado en la URL)
- **Mutación de datos** con **React Server Actions**
- **Error boundaries** con `error.tsx` y `notFound()`
- **Validación server-side + accesibilidad** en formularios
- **Autenticación y rutas protegidas**
- **Metadata/SEO** (títulos, descripciones, social sharing)

Este conjunto es exactamente el temario que cubre el curso del Dashboard App. :contentReference[oaicite:2]{index=2}

---

## Stack / Tecnologías

- Next.js (App Router)
- React
- TypeScript
- Tailwind (si se siguió el curso)
- Server Components & Suspense
- React Server Actions (mutaciones)
- Auth (NextAuth.js + Proxy según el curso)

El curso está diseñado para construir un dashboard con datos y features “de mundo real”. :contentReference[oaicite:3]{index=3}

---

## Estructura típica (App Router)

La demo sigue el patrón del App Router:

```txt
app/
  layout.tsx           # layout raíz (persistente)
  page.tsx             # landing / entrypoint
  dashboard/
    layout.tsx         # layout del dashboard
    page.tsx           # overview del dashboard
    invoices/
      page.tsx         # listado con search/paginación
      [id]/
        page.tsx       # detalle/edición (si aplica)
  api/                 # route handlers (si se usan)
  error.tsx            # error boundary de ruta
  not-found.tsx        # 404 específico
  loading.tsx          # streaming / skeletons

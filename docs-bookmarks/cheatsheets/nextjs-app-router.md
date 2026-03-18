[ Home](../README.md)

---

# Next.js App Router quick map

## File conventions (app/)
- `page.tsx` route entry
- `layout.tsx` shared layout
- `loading.tsx` route-level skeleton
- `error.tsx` error boundary
- `route.ts` Route Handler (API)

## Server vs Client
- Server Components by default.
- Add `"use client"` for components needing hooks, browser APIs, event handlers.

## Data fetching
- Prefer server-side fetching for initial render.
- Client-side fetching for highly interactive dashboards (often + TanStack Query).

## REST endpoints
- Route Handlers: `app/api/.../route.ts`
- Or call your FastAPI/Express backend from Next (BFF pattern).

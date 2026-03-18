[ Home](../README.md)

---

# React Router quick patterns (v6+)

## Route layout
- Layout routes wrap nested routes and render an `<Outlet />`.

## Data Router (loaders/actions) notes
- Loaders are great for REST reads (GET).
- Actions are great for writes (POST/PUT/DELETE) + form handling.
- If you also use TanStack Query, decide one "source of truth" for server state.

## Common UI patterns
- URL is state: use search params for filters/sorting/pagination.
- Use `defer`/streaming patterns if applicable, otherwise show skeletons.

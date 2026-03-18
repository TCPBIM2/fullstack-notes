# Express REST API skeleton (TypeScript-friendly)

## Minimal structure
- `app.ts` create app, middleware, routes, error handler
- `server.ts` start listening
- `routes/*.ts` route modules
- `controllers/*.ts` request handlers
- `services/*.ts` business logic

## Patterns

### Async handler wrapper
```ts
export const asyncHandler =
  (fn: any) =>
  (req: any, res: any, next: any) =>
    Promise.resolve(fn(req, res, next)).catch(next);
```

### Central error handler
```ts
app.use((err, req, res, next) => {
  const status = err.statusCode ?? 500;
  res.status(status).json({
    error: err.name ?? "Error",
    message: err.message ?? "Internal Server Error",
  });
});
```

### REST conventions
- GET /items
- GET /items/:id
- POST /items
- PUT/PATCH /items/:id
- DELETE /items/:id

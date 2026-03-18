# HTTP + REST basics

## Status codes (common)
- 200 OK (success)
- 201 Created (resource created)
- 204 No Content (success, no body)
- 400 Bad Request (validation)
- 401 Unauthorized (not authenticated)
- 403 Forbidden (authenticated but not allowed)
- 404 Not Found
- 409 Conflict (unique constraint, versioning)
- 422 Unprocessable Entity (common for validation)
- 429 Too Many Requests (rate limiting)
- 500 Internal Server Error

## REST guidelines (practical)
- Use nouns for resources (`/users`, `/messages`)
- Use query params for filtering/pagination (`?q=`, `?page=`, `?limit=`)
- Use consistent error shape (code/message/details)
- Version API when needed (`/v1/...`) and deprecate intentionally

## Auth patterns
- Session cookies for web apps (CSRF considerations)
- Bearer tokens (JWT or opaque) for APIs

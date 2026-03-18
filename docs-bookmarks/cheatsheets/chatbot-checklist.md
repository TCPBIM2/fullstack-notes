[ Home](../README.md)

---

# Chatbot app checklist (web + REST backend)

## Core pieces
- Chat UI: message list, streaming indicator, retry, stop/cancel
- Backend: REST endpoint to create/run a turn; optionally WebSocket/SSE streaming
- Safety: input validation, rate limits, content filtering (as needed)
- Observability: logs + request IDs + latency metrics

## Data model (minimal)
- Conversation
- Message (role, content, created_at)
- Tool calls (optional)

## Streaming
- Browser: EventSource (SSE) or WebSocket
- Backend:
  - FastAPI: SSE via StreamingResponse or WebSocket routes
  - Express: SSE headers + res.write chunks

## Reliability
- Timeouts + retries (idempotency keys for POST where needed)
- Persist messages before/after model call (avoid losing history)

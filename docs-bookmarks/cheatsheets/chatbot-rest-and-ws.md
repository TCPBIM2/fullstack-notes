[ Home](../README.md)

---

# Chatbot backend: REST (simple) + WebSockets (realtime)

## Option A: REST (non-streaming) — simplest
### Endpoint shape (example)
- `POST /api/chat`
Request:
```json
{
  "conversation_id": "c_123",
  "messages": [
    { "role": "user", "content": "Hello" }
  ]
}
```

Response:
```json
{
  "conversation_id": "c_123",
  "message": { "role": "assistant", "content": "Hi! How can I help?" }
}
```

### Implementation notes
- Validate request body (FastAPI/Pydantic or Zod in Node)
- Store messages before + after model call (avoid losing history)
- Use timeouts and return useful error shapes

## Option B: WebSockets — for realtime UX
Use when you need:
- token streaming, partial outputs
- cancel/stop
- tool execution progress
- "agent is thinking" events
- multi-user collaboration

### Message envelope (suggested)
```json
{ "type": "user_message", "conversation_id": "c_123", "content": "Hello" }
```

Server events:
```json
{ "type": "assistant_message", "conversation_id": "c_123", "content": "Hi!" }
```

### Reliability
- Include `request_id` / `event_id`
- Handle reconnect (client resyncs conversation state via REST GET)

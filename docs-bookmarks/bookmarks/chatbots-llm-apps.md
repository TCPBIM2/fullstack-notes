[ Home](../README.md)

---

# Chatbots / LLM Apps (REST + WebSockets)

## Concepts / patterns (high-signal)
- OpenAI Cookbook (examples/patterns): https://cookbook.openai.com/
- Prompt Engineering Guide (community, widely used): https://www.promptingguide.ai/
- RAG overview (LangChain docs entry points): https://python.langchain.com/docs/concepts/rag/

## REST (non-streaming)
Typical flow:
- POST /chat { conversation_id, messages[] } -> { assistant_message, usage?, metadata? }
- Persist the turn server-side, return the assistant message once complete.

## WebSockets (bi-directional realtime)
Use for:
- Typing indicators, tool execution updates, token streaming, cancel/stop, multi-agent UX.

### Web platform
- MDN WebSocket API: https://developer.mozilla.org/en-US/docs/Web/API/WebSocket

### FastAPI
- WebSockets: https://fastapi.tiangolo.com/advanced/websockets/

### Node / Express
Express doesn’t include WebSockets natively; common options:
- ws (popular): https://github.com/websockets/ws
- Socket.IO: https://socket.io/docs/v4/

## Orchestration / RAG toolkits (popular)
- LangChain docs: https://python.langchain.com/docs/
- LlamaIndex docs: https://docs.llamaindex.ai/

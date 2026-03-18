[ Home](../README.md)

---

# Concurrency: JS + Python (quick map)

## JavaScript / Node
- Concurrency is mainly I/O concurrency via the event loop.
- Use `Promise.all` for parallel I/O.
- Use worker threads or a job queue for CPU-heavy tasks.
- Beware unbounded parallelism; use a limiter (p-limit style) for large batches.

## Python
### asyncio
- Best for lots of network I/O with async clients.
- Avoid blocking calls inside `async def`.

### Threads vs processes
- Threads: good for blocking I/O (many libs release GIL for I/O).
- Processes: best for CPU-bound work.

## Web servers
- FastAPI: async endpoints shine when all downstream is async (DB/HTTP).
- Express: async/await is fine, but heavy CPU work blocks the event loop.

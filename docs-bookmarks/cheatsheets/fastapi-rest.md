# FastAPI REST API skeleton

## Layout
- `main.py` app + router include
- `routers/*.py` endpoints
- `schemas.py` Pydantic models
- `services/*.py` business logic
- `deps.py` dependencies (auth, db session, etc.)

## Example patterns

### Router + response model
```py
from fastapi import APIRouter
from pydantic import BaseModel

router = APIRouter(prefix="/items", tags=["items"])

class ItemOut(BaseModel):
    id: int
    name: str

@router.get("/", response_model=list[ItemOut])
async def list_items():
    return [{"id": 1, "name": "demo"}]
```

### Error response
Use `HTTPException` for expected errors, global exception handlers for unexpected errors.

### Concurrency note
- Use `async def` with async drivers/clients (HTTPX, async DB libs) to benefit.
- If you must run CPU-bound work, offload via thread/process pool or a job queue.

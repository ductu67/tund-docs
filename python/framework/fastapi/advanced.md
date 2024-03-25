# Advanced

**FastAPI hỗ trợ các tính năng WebSocket:**

* FastAPI hỗ trợ WebSocket thông qua Starlette framework. Sử dụng WebSocket trong FastAPI bằng cách sử dụng Starlette's WebSocketEndpoint class. Ví dụ:

```python
from fastapi import FastAPI, WebSocket

app = FastAPI()

@app.websocket("/ws")
async def websocket_endpoint(websocket: WebSocket):
    await websocket.accept()
    while True:
        data = await websocket.receive_text()
        await websocket.send_text(f"Message text was: {data}")
```

**Sử dụng custom middleware trong FastAPI"**

* Sử dụng custom middleware trong FastAPI bằng cách sử dụng Starlette's Middleware class.  Ví dụ:

```python
from fastapi import FastAPI
from starlette.middleware.base import BaseHTTPMiddleware

class CustomMiddleware(BaseHTTPMiddleware):
    async def dispatch(self, request, call_next):
        # Your custom logic here before the request is processed
        response = await call_next(request)
        # Your custom logic here after the request is processed
        return response

app = FastAPI()

app.add_middleware(CustomMiddleware)
```

**FastAPI có hỗ trợ các tính năng real-time như Server-Sent Events:**

* FastAPI hỗ trợ Server-Sent Events (SSE) thông qua Starlette framework. Sử dụng SSE trong FastAPI bằng cách sử dụng Starlette's EventSourceResponse class. Dưới đây là một ví dụ về cách sử dụng SSE trong FastAPI:

```python
from fastapi import FastAPI
from starlette.responses import EventSourceResponse

app = FastAPI()

@app.get("/events")
async def events():
    async def event_generator():
        for i in range(10):
            yield {"data": f"Event {i}"}
            await asyncio.sleep(1)

    return EventSourceResponse(event_generator())
```

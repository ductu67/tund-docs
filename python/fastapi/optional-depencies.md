---
description: >-
  Do FastAPI based trên Pydantic và Starlette nên có hỗ trợ thêm 1 số thư viện
  có cũng được không có cũng không sao:
---

# Optional Depencies

Pydantic:

* `ujson`: JSON "parsing" nhanh hơn.
* `email_validator`: validate email.

Starlette:

* `requests`: khi bạn muốn tạo request, dùng `TestClient`.
* `aiofiles`: khi bạn muốn dùng `FileResponse` hoặc `StaticFile`.
* `jinja2`: nếu bạn muốn dùng các mẫu config mặc định.
* `python-multipart`: hỗ trợ "parsing" với request.form().
* `itsdangerous`: hỗ trợ `SessionMiddleware`.
* `graphene`: hỗ trợ `GraphQL`.

FastAPI:

* `uvicorn`: ASGI server phục vụ cho ứng dụng của bạn.
* `orjson`: nếu muốn dùng `ORJSONResponse`.

Nếu muốn dùng hết thư viện trên thì bạn chỉ cần dùng 1 câu lệnh đơn giản.

```none
pip install fastapi[all]
```

---
description: >-
  FastAPI framework, high performance, easy to learn, fast to code, ready for
  production. (tham khảo:
  https://viblo.asia/p/huong-dan-co-ban-framework-fastapi-tu-a-z-phan-1-V3m5W0oyKO7)
---

# FastAPI

**FastApi** là 1 web framework dùng để build API có hiệu năng cao, code dễ học, đơn giản nhưng cũng hỗ trợ tốt cho việc làm sản phẩm.

* **Fast**: Hiệu suất cao ngang với NodeJS và Go.
* **Fast to code**: Code nhanh hơn, tốc độ code các features tăng khoảng 200 đến 300 %.
* **Fewer bugs**: do đơn giản nên giảm số bugs của developer đến 40%.
* **Intuitive**: hỗ trợ code dễ hơn với tự động gợi ý, debug cần ít thời gian hơn so với trước.
* **Easy**: được thiết kế sao cho dễ dùng dễ học.
* **Short**: Tối thiểu việc lặp code. Các tham số truyền vào có nhiều tính năng. Ít bugs.
* **Robust**: hiệu năng mạnh mẽ, có thể tương tác API qua docs.

**FastAPI** được build dựa trên:

* **OpenAPI** (trước có tên Swagger) - giao diện dễ nhìn và dễ sử dụng.
* Web được support bởi **Starlette**,&#x20;
* Data được support bởi **Pydantic**.

**FastAPI**  cần ASGI server khi deploy sản phẩm như Uvicorn hoặc Hypercorn.g SGI là tiêu chuẩn cho cả `synchronous` và `asynchronous` `Python apps`. ASGI phù hợp với tất cả ứng dụng sử dụng WSGI

```
pip install uvicorn
```

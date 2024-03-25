# Routing và Dependency Injection

Đ**ịnh nghĩa một route trong FastAPI**

* Để định nghĩa một route trong FastAPI,  sử dụng các decorator như `@app.get`, `@app.post`, `@app.put`, `@app.delete` tương ứng với các phương thức HTTP. Ví dụ:

```python
from fastapi import FastAPI

app = FastAPI()

@app.get("/items/")
async def read_items():
    return {"message": "Hello World"}
```

**FastAPI hỗ trợ path parameters, query parameters, và request body:**

* FastAPI hỗ trợ path parameters thông qua cú pháp `{parameter}` trong định nghĩa route. Ví dụ: `/items/{item_id}`.
* Query parameters có thể được truyền trong URL và được đọc thông qua các tham số của hàm route. Ví dụ: `/items/?limit=10&offset=0`.
* FastAPI tự động phân tích và deserialize dữ liệu được gửi trong request body dựa trên kiểu dữ liệu của tham số của hàm route. Dữ liệu có thể là JSON, form data, hoặc multipart form. Ví dụ:

```python
from pydantic import BaseModel

class Item(BaseModel):
    name: str
    description: str = None
    price: float
    tax: float = None

@app.post("/items/")
async def create_item(item: Item):
    return item

```

**FastAPI thực hiện dependency injection và để sử dụng nó trong ứng dụng:**

* FastAPI thực hiện dependency injection bằng cách sử dụng parameter của hàm route. FastAPI tự động tạo và quản lý các instance của các dependencies và chuyển chúng vào các hàm route khi cần.
* Để sử dụng dependency injection, chỉ cần khai báo các tham số cho các hàm route của mình và FastAPI sẽ tự động cung cấp các dependency tương ứng. Ví dụ:

```python
from fastapi import Depends

async def get_db():
    db = DBSession()
    try:
        yield db
    finally:
        db.close()

@app.get("/items/")
async def read_items(db: DBSession = Depends(get_db)):
    return db.query(Item).all()
```

`DBSession` là một dependency cần được sử dụng trong hàm `read_items()`. FastAPI tự động tạo một instance của `DBSession` và chuyển nó vào hàm `read_items()` thông qua tham số `db`.


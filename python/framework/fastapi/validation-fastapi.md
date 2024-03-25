# Validation FastAPI

**FastAPI hỗ trợ validation data:**

* FastAPI sử dụng Pydantic, một thư viện validation mạnh mẽ, để thực hiện validation data. Khi định nghĩa một Pydantic model cho dữ liệu đầu vào, FastAPI sẽ tự động thực hiện validation dữ liệu dựa trên các rules định nghĩa trong model đó. Nếu dữ liệu không hợp lệ, FastAPI sẽ trả về một response với thông báo lỗi và status code tương ứng.

<pre class="language-python"><code class="lang-python"><strong>from pydantic import BaseModel
</strong>
class Item(BaseModel):
    name: str
    price: float
    
@app.post("/items/")
async def create_item(item: Item):
    return {"name": item.name, "price": item.price}
</code></pre>

Pydantic models có thể được sử dụng cho việc validation ở nhiều vị trí trong FastAPI, bao gồm:

* Validation của request body trong các phương thức POST, PUT, PATCH.
* Validation của path parameters và query parameters trong URL.
* Validation của response body trả về từ các phương thức route.
* Validation của các dependency được inject vào các hàm route, như làm dependency của một hàm `Depends()`.

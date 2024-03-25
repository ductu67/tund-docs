# Authentication and Authorization

**Thực hiện authentication và authorization trong FastAPI:**

FastAPI không có built-in authentication mechanism, nhưng nó hỗ trợ các phương thức authentication như Basic Authentication, OAuth2, JWT (JSON Web Tokens), API Key Authentication, và nhiều hơn nữa thông qua việc tích hợp với các thư viện và middleware bên thứ ba.

**Áp dụng middleware cho việc xác thực trong FastAPI?**

* Sử dụng các hàm middleware và phương thức dependency injection. ó thể định nghĩa một middleware để xác thực người dùng, sau đó áp dụng nó cho các route cần bảo vệ. Ví dụ:

```python
from fastapi import FastAPI, Depends, HTTPException
from fastapi.security import OAuth2PasswordBearer

app = FastAPI()
oauth2_scheme = OAuth2PasswordBearer(tokenUrl="token")

async def get_current_user(token: str = Depends(oauth2_scheme)):
    # logic để xác thực và lấy thông tin người dùng từ token
    return token

@app.get("/users/me")
async def read_users_me(current_user: str = Depends(get_current_user)):
    return {"current_user": current_user}

```

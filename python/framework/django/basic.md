# Basic

**Giải thích ý nghĩa của migrations trong Django và làm thế nào để chạy migrations:**

* Migrations là cách Django theo dõi các thay đổi trong cấu trúc cơ sở dữ liệu.
* Khi bạn thực hiện các thay đổi trong models, bạn cần tạo migrations để cập nhật cấu trúc cơ sở dữ liệu.

**Làm thế nào để tạo một custom middleware trong Django?**

* Để tạo một custom middleware trong Django, cần định nghĩa một class kế thừa từ `MiddlewareMixin` và định nghĩa phương thức `__init__` và/hoặc `__call__` để xử lý các request và response.&#x20;
* Middleware có thể thực hiện các công việc như xác thực, ghi log, quản lý session, và nhiều công việc khác.

```python
# myapp/middleware.py

import logging
from django.utils.deprecation import MiddlewareMixin

logger = logging.getLogger(__name__)

class LogMiddleware(MiddlewareMixin):
    def process_request(self, request):
        logger.info(f"Request: {request.method} {request.path}")

    def process_response(self, request, response):
        logger.info(f"Response: {response.status_code}")
        return response
        
# settings.py
MIDDLEWARE = [
    # Other middleware classes...
    'myapp.middleware.LogMiddleware',
]   
```

**Giải thích ý nghĩa của CSRF và cách xử lý CSRF trong Django:**

* CSRF (Cross-Site Request Forgery) là một kỹ thuật tấn công trong đó hacker có thể thực hiện các hành động không mong muốn trên trang web của người dùng khi họ đã đăng nhập.
* Để xử lý CSRF trong Django, bạn cần bật middleware `django.middleware.csrf.CsrfViewMiddleware` và sử dụng template tag `{% csrf_token %}` trong các biểu mẫu (forms) của bạn

**Giải thích ý nghĩa của Django's ORM (Object-Relational Mapping) và cách sử dụng nó:**

* ORM trong Django là một lớp trừu tượng hóa dữ liệu cơ sở dữ liệu thành các đối tượng Python, giúp cho việc tương tác với cơ sở dữ liệu trở nên dễ dàng hơn.&#x20;
* Bằng cách định nghĩa các models, bạn có thể thực hiện các thao tác CRUD (Create, Read, Update, Delete) trên cơ sở dữ liệu mà không cần viết các câu truy vấn SQL.

**Làm thế nào để triển khai ứng dụng Django/DRF lên môi trường sản phẩm (production environment)?**

* Để triển khai ứng dụng Django/DRF lên môi trường sản phẩm, bạn cần thiết lập một máy chủ web như Nginx hoặc Apache để phục vụ các yêu cầu HTTP, và sử dụng một WSGI server như Gunicorn hoặc uWSGI để chạy ứng dụng Django/DRF.&#x20;
* Cấu hình các biến môi trường (environment variables), quản lý static files và media files, và cài đặt một hệ thống log để ghi log cho ứng dụng của bạn.

**Làm thế nào để xử lý file uploads trong DRF:**

* Để xử lý file uploads trong DRF, ử dụng serializers với trường `FileField` hoặc `ImageField`. DRF sẽ tự động xử lý các yêu cầu POST chứa file uploads và lưu trữ file vào đường dẫn được chỉ định trong settings của bạn.

\

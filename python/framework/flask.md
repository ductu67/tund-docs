---
description: https://flask.palletsprojects.com/en/3.0.x/
---

# Flask

* **Flask** là một micro-framework web Python nhẹ và linh hoạt. Nó cho phép xây dựng các ứng dụng web từ các thành phần cơ bản như routing, templates, và handling requests.
* Flask hoạt động bằng cách sử dụng mô hình WSGI (Web Server Gateway Interface), nơi mỗi request từ client được chuyển đến ứng dụng Flask, được xử lý bởi các hàm hoặc classes được gọi là view functions, và sau đó trả về một response.
* Flask không yêu cầu các dependencies ngoài cơ bản, điều này làm cho nó trở thành một lựa chọn phổ biến cho việc xây dựng các ứng dụng web nhỏ và đơn giản.

**Giải thích ý nghĩa của routing trong Flask và cách định nghĩa một route:**

* Routing trong Flask là cách mà ứng dụng quyết định cách xử lý một request HTTP từ client dựa trên URL được yêu cầu. Mỗi route được liên kết với một view function, mà khi được gọi, sẽ thực hiện xử lý và trả về response tương ứng.
* Để định nghĩa một route trong Flask, bạn sử dụng decorator `@app.route()` trên một hàm. Ví dụ:

```python
from flask import Flask

app = Flask(__name__)

# Xử lý yêu cầu GET
@app.route('/', methods=['GET'])
def handle_get_request():
    return 'Hello, this is a GET request!'

```

**Giải thích ý nghĩa của Jinja2 trong Flask và cách sử dụng nó để render templates:**

* Jinja2 là một engine template Python mạnh mẽ, dùng để render các templates HTML. Trong Flask, Jinja2 được sử dụng để tạo các trang web động bằng cách lồng các biến, điều kiện, và vòng lặp vào trong các file templates HTML.
* Để sử dụng Jinja2 trong Flask, bạn cần tạo một thư mục `templates` trong dự án Flask của mình và đặt các file template HTML trong đó. Sau đó, bạn có thể render các templates này bằng cách sử dụng hàm `render_template()` và truyền các biến cần thiết. Ví dụ:

```python
from flask import render_template

@app.route('/')
def index():
    name = 'John'
    return render_template('index.html', name=name)
```

**Flask có hỗ trợ caching không? Nếu có, làm thế nào để thực hiện caching trong Flask:**

* Flask không có hỗ trợ caching mặc định, nhưng có thể sử dụng các extension như Flask-Caching để thực hiện caching trong Flask. Để sử dụng Flask-Caching,  bạn cần pip

**Flask có hỗ trợ CORS không? Nếu có, làm thế nào để xử lý CORS trong Flask?**

* Flask không cung cấp hỗ trợ CORS mặc định. Tuy nhiên, bạn có thể sử dụng extension Flask-CORS để xử lý CORS trong Flask.

**Làm thế nào để xử lý authentication và authorization trong Flask?**

* Để xử lý authentication và authorization trong Flask, bạn có thể sử dụng các extension như Flask-Login, Flask-JWT-Extended hoặc Flask-Security. Các extension này cung cấp các công cụ để xác thực người dùng, quản lý session, và kiểm soát quyền truy cập.

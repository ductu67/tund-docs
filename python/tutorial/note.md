# NOTE

**Tối ưu hóa hiệu suất của mã Python:**

* Sử dụng các cấu trúc dữ liệu hiệu quả như dict, set, list comprehension.
* Tránh sử dụng vòng lặp lớn và thay vào đó sử dụng các hàm tích hợp như map(), filter(), reduce().

**Phân biệt giữa `__getattr__`, `__getattribute__`, và `__setattr__` trong Python:**

* `__getattr__(self, name)`: Phương thức này được gọi khi một thuộc tính không tồn tại được truy cập. Nó cho phép định nghĩa cách xử lý khi thuộc tính không tồn tại.
* `__getattribute__(self, name)`: Phương thức này được gọi khi bất kỳ thuộc tính nào được truy cập, bao gồm cả thuộc tính tồn tại và không tồn tại. Điều này cho phép bạn tùy chỉnh việc truy cập thuộc tính.
* `__setattr__(self, name, value)`: Phương thức này được gọi khi một thuộc tính được gán giá trị. Nó cho phép bạn tùy chỉnh hành vi của việc gán giá trị cho thuộc tính.

**Giải thích ý nghĩa của `__init__` trong Python class:**

* `__init__` là một phương thức đặc biệt trong Python được gọi ngay khi một đối tượng của class được tạo ra.
* Phương thức `__init__` được sử dụng để khởi tạo các thuộc tính của đối tượng và thực hiện các tác vụ khởi tạo khi đối tượng được tạo ra.

**Xử lý và giải quyết vấn đề về bảo mật trong ứng dụng Python:**

* Sử dụng các thư viện và framework bảo mật như Django hay Flaskđể bảo vệ ứng dụng khỏi các cuộc tấn công như SQL injection, cross-site scripting (XSS), cross-site request forgery (CSRF), và injection attacks.
* Sử dụng các thư viện mã hóa như bcrypt để lưu trữ mật khẩu của người dùng một cách an toàn.
* Xác thực và ủy quyền người dùng một cách chặt chẽ, sử dụng các công cụ như JSON Web Tokens (JWT) hoặc OAuth2.
* Kiểm tra và xử lý dữ liệu đầu vào một cách cẩn thận để ngăn chặn các cuộc tấn công từ phía người dùng.
* Thực hiện kiểm tra bảo mật định kỳ và cập nhật các thư viện và dependencies của ứng dụng.

**Hoạt động của garbage collection và kiểm soát việc thu gom rác trong Python:**

* Garbage collection là quá trình tự động thu gom và giải phóng bộ nhớ không còn được sử dụng trong Python.
* Python sử dụng một chiến lược gọi là "reference counting" kết hợp với một thuật toán dò quét (traversing) để thu gom rác.

**Parallel processing trong Python:**

* Python có hỗ trợ parallel processing thông qua các module như `multiprocessing` và `concurrent.futures`.
* Để thực hiện parallel processing trong Python, bạn có thể sử dụng module `multiprocessing` để tạo các tiến trình con và thực thi chúng đồng thời.
* Module `concurrent.futures` cung cấp một cách tiếp cận cao cấp hơn để thực hiện parallel processing thông qua executor và futures.

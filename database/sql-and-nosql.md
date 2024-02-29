# SQL and NOSQL

**Sự Giống:**

1. **Mục Đích Lưu Trữ Dữ Liệu:**
   * **SQL:** Thường được sử dụng cho các ứng dụng có cấu trúc, nhu cầu đặc trưng, và yêu cầu tính nhất quán cao.
   * **NoSQL:** Thường được ưa chuộng trong các ứng dụng đòi hỏi linh hoạt, có khả năng mở rộng, và làm việc với dữ liệu phi cấu trúc.
2. **Ngôn Ngữ Truy Vấn:**
   * **SQL:** Sử dụng ngôn ngữ truy vấn SQL cấu trúc để truy vấn dữ liệu.
   * **NoSQL:** Sử dụng ngôn ngữ truy vấn cụ thể cho từng loại cơ sở dữ liệu, ví dụ như MongoDB

**Sự Khác:**

1. **Cấu Trúc Dữ Liệu:**
   * **SQL:** Lưu trữ dữ liệu theo mô hình bảng, có các hàng và cột với các quan hệ được xác định trước.
   * **NoSQL:** Có nhiều mô hình lưu trữ, bao gồm key-value, document-oriented, column-family, và graph database, không yêu cầu cấu trúc cứng.
2. **Mở Rộng:**
   * **SQL:** Mở rộng thường là dọc theo chiều dọc (vertical scaling) bằng cách tăng cường tài nguyên trên một máy chủ.
   * **NoSQL:** Mở rộng thường là ngang (horizontal scaling) bằng cách thêm máy chủ mới để tăng khả năng chịu tải.
3. **Hiệu Suất và Tính Sẵn Có (Availability):**
   * **SQL:** Thường bet trong hiệu suất cao và tính sẵn có, nhưng đôi khi có thể phức tạp và đắt đỏ khi cần mở rộng.
   * **NoSQL:** Tập trung vào hiệu suất và sẵn có, thường đơn giản hóa quá trình mở rộng.
4. **ACID vs. BASE:**
   * **SQL:** Đảm bảo ACID (Atomicity, Consistency, Isolation, Durability).
   * **NoSQL:** Thường hướng đến tính chất BASE (Basically Available, Soft state, Eventually consistent), đặc biệt là trong môi trường phân tán.

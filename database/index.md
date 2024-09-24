---
description: >-
  1 cấu trúc dữ liệu đặc biệt giúp tăng tốc độ truy vấn dữ liệu bằng cách giảm
  thiểu số lượng bản ghi cần đọc từ bảng. Hoạt động giống như một cuốn sách có
  mục lục, giúp  tìm kiếm thông tin nhanh hơn.
---

# Index

#### 1. **Tại sao cần sử dụng chỉ mục (Index)?**

* Khi  thực hiện truy vấn mà không có chỉ mục, hệ thống phải quét toàn bộ bảng để tìm dữ liệu -> tốn thời gian.
* **Chỉ mục** -> tối ưu hóa việc tìm kiếm

#### 2. **Cách hoạt động của chỉ mục**

* Chỉ mục tạo ra một cấu trúc dữ liệu riêng biệt (thường là **B-tree** hoặc **Hash**) chứa một phiên bản sắp xếp của các giá trị trong cột hoặc các cột được chỉ định.
* Khi thực hiện truy vấn, cơ sở dữ liệu sẽ tra cứu chỉ mục trước để tìm ra vị trí của dữ liệu cần thiết trong bảng, từ đó giảm số bản ghi phải đọc.

#### 3. **Các loại chỉ mục phổ biến**

* **B-tree Index** (Cây cân bằng):
  * Đây là loại chỉ mục mặc định trong nhiều hệ quản trị cơ sở dữ liệu như MySQL và PostgreSQL.
  * Dữ liệu trong **B-tree** được sắp xếp thứ tự, cho phép tìm kiếm, duyệt, và truy cập nhanh chóng. Nó hữu ích cho các truy vấn có điều kiện **WHERE**, **ORDER BY**, **GROUP BY**, hoặc **DISTINCT**.
* **Hash Index**:
  * Chỉ mục Hash hoạt động tốt với các truy vấn **chính xác** (ví dụ: tìm kiếm theo khóa chính), nhưng không hiệu quả với các truy vấn dải (range queries) như so sánh lớn hơn/nhỏ hơn.
  * Tốt nhất cho các truy vấn **=** hoặc **IN**.
* **GIN Index (Generalized Inverted Index)**:
  * Sử dụng trong PostgreSQL, thường dùng cho các cột kiểu dữ liệu không truyền thống như **JSONB**, **HStore**, hoặc mảng.
  * Hiệu quả trong việc tìm kiếm trên các cấu trúc dữ liệu phức tạp.
* **Full-text Index**:
  * Chỉ mục toàn văn, hữu ích cho việc tìm kiếm văn bản trong các hệ thống quản lý văn bản hoặc tìm kiếm trong chuỗi dài.
  * Nó chia văn bản thành các từ khóa và tạo chỉ mục cho từng từ khóa, giúp truy vấn tìm kiếm văn bản nhanh hơn.
* **Composite Index** (Chỉ mục kết hợp):
  * Một chỉ mục có nhiều cột. Nó hữu ích khi thường xuyên lọc dữ liệu dựa trên nhiều cột cùng lúc.
  * Khi tạo chỉ mục nhiều cột, thứ tự của các cột trong chỉ mục là rất quan trọng.

#### 4. **Khi nào nên tạo chỉ mục?**

* **Truy vấn chậm**: Nếu các truy vấn mất nhiều thời gian để thực thi, đặc biệt là các truy vấn trên các cột trong điều kiện **WHERE**, **JOIN**, hoặc **ORDER BY**, thì việc thêm chỉ mục có thể cải thiện hiệu suất.
* **Khóa chính (Primary Key)**: Tạo chỉ mục trên các cột khóa chính là điều cần thiết vì mỗi lần truy vấn thường xuyên liên quan đến khóa chính.
* **Khóa ngoại (Foreign Key)**: Tạo chỉ mục trên các khóa ngoại để cải thiện hiệu suất trong các phép nối.
* **Cột thường xuyên truy vấn**: Nếu thường xuyên truy vấn hoặc lọc dữ liệu theo một cột cụ thể, việc tạo chỉ mục trên cột đó có thể giúp tăng tốc độ truy vấn.

#### 5. **Hạn chế của chỉ mục**

* **Bộ nhớ**: Mỗi chỉ mục chiếm một lượng bộ nhớ riêng. Nếu tạo quá nhiều chỉ mục, có thể gặp vấn đề về bộ nhớ và không gian lưu trữ.
* **Hiệu suất ghi**: Chỉ mục cải thiện tốc độ truy vấn đọc, nhưng sẽ làm chậm các thao tác ghi (INSERT, UPDATE, DELETE) vì hệ quản trị cơ sở dữ liệu cần phải cập nhật chỉ mục mỗi khi có thay đổi dữ liệu.
* **Không phải mọi truy vấn đều sử dụng chỉ mục**: Không phải lúc nào cơ sở dữ liệu cũng sử dụng chỉ mục. Nếu tạo chỉ mục không hợp lý hoặc truy vấn quá phức tạp, hệ quản trị có thể bỏ qua chỉ mục.

#### 6. **Chiến lược tối ưu hóa chỉ mục**

* **Phân tích truy vấn (Query Plan)**: Kiểm tra kế hoạch truy vấn (query plan) để xem liệu chỉ mục có được sử dụng hay không. Ví dụ, sử dụng lệnh **EXPLAIN** trong MySQL hoặc PostgreSQL.
* **Cân nhắc thứ tự cột trong Composite Index**: Đặt các cột mà thường lọc dữ liệu đầu tiên, các cột ít quan trọng hơn sau.
* **Xóa chỉ mục không cần thiết**: Nếu có quá nhiều chỉ mục hoặc chỉ mục không được sử dụng, nên xóa đi để tiết kiệm tài nguyên và cải thiện hiệu suất ghi.

#### 7. **Ví dụ**

*   **Tạo chỉ mục trong MySQL**:

    ```sql
    CREATE INDEX idx_customer_name ON customers (name);
    ```

    * Chỉ mục này sẽ tăng tốc độ truy vấn tìm kiếm khách hàng theo tên.
*   **Tạo chỉ mục kết hợp trong PostgreSQL**:

    ```sql
    CREATE INDEX idx_order_date_customer ON orders (order_date, customer_id);
    ```

    * Chỉ mục này sẽ hiệu quả khi truy vấn dựa trên cả ngày đặt hàng và mã khách hàng.


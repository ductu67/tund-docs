---
description: >-
  SQL (Structured Query Language) là một ngôn ngữ lập trình dành cho quản lý và
  tương tác với cơ sở dữ liệu quan hệ.
---

# SQL

1. **Mục Đích:**
   * SQL được thiết kế để truy vấn, cập nhật và quản lý dữ liệu trong cơ sở dữ liệu quan hệ.
2. **Câu Lệnh Cơ Bản:**
   * **SELECT:** Truy vấn dữ liệu từ bảng. Với điều kiện là WHERE
   * **INSERT:** Thêm dữ liệu mới vào bảng.
   * **UPDATE:** Cập nhật dữ liệu trong bảng.
   * **DELETE:** Xóa dữ liệu từ bảng.
3. **JOIN:** kết hợp dữ liệu từ nhiều bảng
   * INNER JOIN, Trả về các hàng có kết quả khớp từ cả hai bảng.
   * LEFT JOIN, Trả về tất cả các hàng từ bảng bên trái và các hàng khớp từ bảng bên phải. Nếu không có kết quả khớp, các cột từ bảng bên phải sẽ chứa giá trị NULL.
   * RIGHT JOIN. ngược lại right join
4. **Hàm Aggregation:**
   * COUNT(), SUM(), AVG(), MIN(), MAX() tính toán giá trị dựa trên dữ liệu trong cột, và việc nhóm dữ liệu bằng GROUP BY.
5. **Ràng Buộc (Constraints):**
   * PRIMARY KEY: Định nghĩa khóa chính cho bảng.
   * FOREIGN KEY: Xác định mối quan hệ giữa các bảng.
   * UNIQUE: Đảm bảo giá trị duy nhất trong một cột.
   * NOT NULL: Không chấp nhận giá trị NULL trong cột.
6. **Quản Lý Cơ Sở Dữ Liệu:**
   * CREATE DATABASE: Tạo cơ sở dữ liệu mới.
   * CREATE TABLE: Định nghĩa bảng mới trong cơ sở dữ liệu.
7. **Quyền và Bảo Mật:**
   * GRANT: Cấp quyền truy cập cho người dùng.
   * REVOKE: Thu hồi quyền truy cập.
8. **Stored Procedures và Triggers:**
   * CREATE PROCEDURE: Định nghĩa thủ tục lưu trữ.

<pre class="language-sql"><code class="lang-sql">CREATE PROCEDURE GetCustomerInfo 
    @CustomerID INT 
AS 
BEGIN 
<strong>    SELECT * FROM Customers WHERE CustomerID = @CustomerID; 
</strong>END;
</code></pre>

* CREATE TRIGGER: một đoạn mã SQL tự động thực hiện một hành động khi một sự kiện xảy ra trong cơ sở dữ liệu. VD: INSERT, UPDATE, hoặc DELETE từ một bảng cụ thể.

VD: Giả sử bạn muốn theo dõi việc cập nhật giá trị của cột `Balance` trong bảng `Accounts` và lưu thông tin về sự thay đổi vào một bảng lịch sử (`BalanceHistory`).

```sql
CREATE TRIGGER UpdateBalanceHistory
ON Accounts
AFTER UPDATE
AS
BEGIN
    INSERT INTO BalanceHistory (AccountID, OldBalance, NewBalance, UpdateDate)
    SELECT 
        AccountID, 
        DELETED.Balance AS OldBalance, 
        INSERTED.Balance AS NewBalance,
        GETDATE() AS UpdateDate
    FROM DELETED
    INNER JOIN INSERTED ON DELETED.AccountID = INSERTED.AccountID;
END;
```

1. **Optimization và Indexing:**
   * Thành thạo trong việc sử dụng chỉ mục (INDEX) để tối ưu hóa hiệu suất truy vấn:
   * **Tăng Tốc Truy Vấn:**
     * Chỉ mục giúp tăng tốc quá trình truy vấn dữ liệu bằng cách cung cấp một cách hiệu quả để tìm kiếm, lọc, và sắp xếp dữ liệu.
     * Giúp giảm phạm vi của cuộc tìm kiếm.
   * **Giảm Tải Cho Hệ Thống:**
     * Giúp giảm tải cho hệ thống cơ sở dữ liệu vì nó giúp giảm thời gian và tài nguyên cần thiết để thực hiện các truy vấn.
   * **Tăng Tốc Đọc và Ghi:**
     * Cải thiện hiệu suất đọc và ghi dữ liệu bằng cách tối ưu hóa cách dữ liệu được lưu trữ và truy cập.
   * **Hỗ Trợ Ràng Buộc Duy Nhất:**
     * Đảm bảo rằng giá trị trong một cột là duy nhất, giúp kiểm soát tính chính xác và nhất quán của dữ liệu.
2.  **Câu Lệnh SQL Phức Tạp:**

    * Có khả năng xử lý câu lệnh SQL phức tạp, sử dụng CASE-WHEN, IF-ELSE, và các biểu thức logic.
    * #### Sử Dụng `CASE WHEN`

    ```sql

    SELECT ProductName, Score,
        CASE
            WHEN Score > 80 THEN 'High'
            WHEN Score BETWEEN 60 AND 80 THEN 'Medium'
            ELSE 'Low'
        END AS Rating
    FROM Products;
    ```

**Sử Dụng `IF-ELSE`**

```sql
CREATE PROCEDURE UpdateProductStatus 
    @ProductId INT 
AS 
BEGIN 
    DECLARE @StockQuantity INT; 
    DECLARE @Status VARCHAR(20);
    SELECT @StockQuantity = StockQuantity FROM Products WHERE ProductID = @ProductId;
    IF @StockQuantity > 0
        SET @Status = 'In Stock';
    ELSE
        SET @Status = 'Out of Stock';

    UPDATE Products SET Status = @Status WHERE ProductID = @ProductId;
END;
```


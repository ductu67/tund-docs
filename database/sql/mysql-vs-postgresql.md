# MySQL vs PostgreSQL

## So sánh hiệu năng khi hệ thống có lượng truy cập đồng thời lớn.

1. **MVCC (Multi-Version Concurrency Control)**

**MySQL (InnoDB)**: Dùng row versions nhưng có thể gặp vấn đề với gap locking.

**PostgreSQL**: Quản lý các phiên bản dòng tốt hơn, không cần khóa dòng, tối ưu cho giao dịch song song.

* **Khả năng xử lý giao dịch đồng thời**:
  * **MySQL**: Xử lý tốt với tải nhỏ/trung bình nhưng có thể gặp deadlock khi truy cập đồng thời lớn.
  * **PostgreSQL**: Xử lý tốt các giao dịch song song, ít xảy ra lock contention hơn.
* **Hiệu năng đọc/ghi**:
  * **MySQL**: Ghi đồng thời có thể giảm hiệu suất, nhưng truy vấn đọc vẫn hiệu quả.
  * **PostgreSQL**: Duy trì hiệu suất ổn định hơn trong đọc/ghi đồng thời.
* **Thu dọn dữ liệu cũ**:
  * **MySQL**: Tự động thu dọn phiên bản dữ liệu cũ.
  * **PostgreSQL**: Cần VACUUM để thu dọn, nhưng khi tối ưu tốt vẫn duy trì hiệu suất.
* **Tối ưu hóa**:
  * **MySQL**: Dễ tối ưu cho hệ thống nhỏ/trung bình.
  * **PostgreSQL**: Cung cấp nhiều tùy chọn cấu hình mạnh mẽ hơn, phù hợp với hệ thống lớn.
* **Kết luận**:
  * **MySQL**: Phù hợp với tải nhỏ/trung bình.
  * **PostgreSQL**: Hiệu quả hơn khi có truy cập đồng thời lớn và nhiều giao dịch ghi.

### So sánh hiệu năng khi xử lý câu lệnh SQL

1.Cú Pháp -> 2.Ngữ  Nghĩa -> 3.Chiến lược thực thi -> 4.Phân tích -> 5.Tạo chiên lược thực thi.\
Mục đích: Chọn Cost nhỏ nhất&#x20;

PostgresSQL:

* Phân tích chi tiết hơn rất nhiều
* Dùng nhiều yếu tố hơn để đánh giá COST một câu lệnh

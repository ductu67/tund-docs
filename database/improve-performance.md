# Improve Performance

Nguyên lý 1: Page/Block - Đơn vị nhỏ nhất khi làm việc Database

* Pages/block là đơn vị nhỏ nhất  có đơn vị là 8K (Oracle gọi là block, MySQL là pages)
* Row không phải đơn vị nhỏ nhất. \
  Ví dụ:  Pages là A4, Row là 1 dòng trên A4. Vậy nên A4 là đơn vị nhỏ nhất.

<figure><img src="../.gitbook/assets/image (4).png" alt=""><figcaption></figcaption></figure>



### Nguyên lý 2: Cache và 2 cơ chế Read, Write trong Database

* Cache làm việc với đơn vị nhỏ nhất là Pages/Block. Vì vậy cache sẽ cache tất cả các page dẫn đến ảnh hưởng đến hiệu năng.&#x20;
* Read trong database:
  * B1: Tìm bản ghi ở pages nào
  * B2: Đưa pages đó lên memory (Cache)
* Write trong database:
  * B1: Đưa pages lên memory(Cache)
  * B2: Thực Thi thay đổi (Update/Delete/Insert)
  * B3: Ghi từ bộ nhớ xuống
* Cache theo block/page: &#x20;
  * Hầu hết các Database, khi thực hiện order\_by - tính toán thì không lưu kết quả - không lưu cache
  * Còn với Oracle thì khi thực hiện order\_by - tính toán thì lưu kết quả - Result Cache

### Nguyên lý 3: Cost - Chiến lược thực thi - SQL Execution Plan

<figure><img src="../.gitbook/assets/image (6).png" alt=""><figcaption></figcaption></figure>

* Chiến lực thực thi là bản đồ, con đường để lấy dữ liệu - dựa theo chi phí thực hiện nhỏ nhất
* Cách truy cập vào index, Cách truy cập vào table

### Tổng kết nguyên lý 3 + 2 và áp dụng trong các mô hình triển khai Database thực tế

<figure><img src="../.gitbook/assets/image (8).png" alt=""><figcaption></figcaption></figure>

Mô hình standlone - single:  Khi hệ thống lớn sẽ không đáp ứng được

Mô hình Primary (write) - StandBy/Secondary(read)

<figure><img src="../.gitbook/assets/image (11).png" alt=""><figcaption><p>Standlone and Primary - StandBy</p></figcaption></figure>

Mô hình Oracle RAC:  Sử dụng 2 máy chủ -  bộ nhớ chung --> không bị corupt dữ liệu.

<figure><img src="../.gitbook/assets/image (9).png" alt=""><figcaption><p>Oracle RAC</p></figcaption></figure>

### Khi nào Table có ít bản ghi nhưng lại chiếm nhiều Blocks dữ liệu ?

* Khi database bị phân mảnh dữ liệu khi thực hiện nhiều câu lệnh delete

### Nếu dữ liệu cần xử lý không vừa với Memory thì sao ?

* Cache --> Physical Read: Tỉ lệ Physical Read và Logical Read là bao nhiêu. (Trong Oracle - AWR)

### Pages/ Blocks có thể chưa dữ liệu của nhiều Tables không?

* Có chứa nhiều bản ghi của các Table khác nhau

### 1 Pages / Blocks có thể khác 8KB hay không ?

* Có thể cấu hình 16K, 32K.

### Khi nào Index chậm hơn Full Table Scan ?

* Ví dụ. Oto và xe máy khi chở số lượng người lớn.

### Vì sao Index giúp tăng tốc Query


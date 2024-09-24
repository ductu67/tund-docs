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

* Index tạo ra 1 table nhỏ để dung lượng nhỏ để query. Ví dụ 1 bảng chỉ có tên cho user

### Index có hiệu quả không nếu nhiều dữ liệu thỏa mãn điều kiện WHERE?

* Thì sử dụng quét full bảng để nhanh hơn index. Do khi quét index các record nằm ở nhiều page khác nhau nên sẽ dẫn đến việc truy xuất lâu hơn

### Hiệu quả Index đối với câu lệnh làm việc trên nhiều cột

* Với câu lệnh Where A=1 and B=2 and C=3 | Where B=2 and A=1 and C=3 ==> không khác nhau, không ảnh hưởng.
* Với Index(A,B,C) != Index(A,B,C) != Index(B,C,A)

### Thứ tự cột trong Index ảnh hưởng hiệu năng ra sao?

* Index - A, -B, -C --> Index mổ cò
* Index tổ hợp các cột: Index (Name, ity) != (City, Name)  ===> Danh sách trả ra khác nhau nên sẽ khác nhau

### Lưu ý - hiểu lầm về FULL TABLE SCAN

* VD: Select \* from users Where downvotes > 0 -- Cost = 12.000
* VD: Select \* from users Where downvotes > 0 fetch first 10 row only -- Cost = 2
* Không phải Full ble Scan là quét hết dữ liệu. Vì nó hoạt động sẽ nhảy lên block đầu tiền và tìm dữ liệu và số lượng cụ thể.

### Chi tiết về cơ chế CACHE - một khía cạnh của nguyên lý 3 + 2

* &#x20;VD1: Select \* from users; --> Hệ thống cache toàn bộ các block của bảng users
* VD2: Select \* from users order by downvotes; -> Hệ thống phải lấy tất cả các block dữ liệu của bảng user -> Sử dụng giải thuật sort .. -> Không phải block dữ liệu trong Table nên là không lưu được

\-> Select /\*+ RESULT\_CACHE \*/ \* from users order by downvotes; Cache query đầu tiên những query tiếp theo sẽ nhanh hơn vì dùng cache trên. Lưu ý: Vì chỉ cần thay đổi dữ liệu sẽ phải lưu cache lại -> nên dùng dữ liệu tĩnh - dữ liệu không thay đổi.

\-> Cache không giữ mãi trong database dựa trên giải thuật ưu tiền sử dụng nhiều.






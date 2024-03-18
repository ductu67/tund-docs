# Networking Tools

Các công cụ mạnh mẽ được cung cấp để giúp quản lý và kiểm tra mạng.&#x20;

1.  **ping**: Sử dụng để kiểm tra kết nối mạng đến một máy chủ hoặc địa chỉ IP bằng cách gửi gói tin ICMP Echo Request và nhận gói tin Echo Reply.

    Ví dụ: `ping google.com`
2.  **traceroute**: Dùng để xác định đường đi của các gói tin từ máy tính của bạn đến một máy chủ hoặc địa chỉ IP bằng cách hiển thị tất cả các nút mạng trên đường đi.

    Ví dụ: `traceroute google.com`&#x20;
3. **mtr:** Kết hợp chức năng traceroute và ping vào một công cụ chẩn đoán duy nhất.
4. **nmap**: Quét máy chủ để tìm cổng mở.
5. **tcpdump:** Dump lưu lượng truy cập trên mạng.
6.  **netstat**: Cung cấp thông tin về kết nối mạng, bảng định tuyến, giao thức mạng và cổng mạng đang sử dụng trên máy tính của bạn.

    Ví dụ: `netstat -tuln`
7.  **nslookup**: Sử dụng để truy vấn tên miền hoặc địa chỉ IP của một máy chủ DNS.

    Ví dụ: `nslookup google.com`
8.  **dig**: Cũng tương tự như nslookup, dig (Domain Information Groper) được sử dụng để truy vấn tên miền và trả về thông tin DNS chi tiết.

    Ví dụ: `dig google.com`
9.  **ifconfig/ip**: Dùng để hiển thị thông tin về các thiết bị mạng, bao gồm cả địa chỉ IP, địa chỉ MAC, và cài đặt mạng khác.

    Ví dụ: `ifconfig` hoặc `ip addr`
10. **curl**: Cung cấp khả năng truy cập và tải xuống tài nguyên từ các máy chủ từ xa, bao gồm cả trang web và API.

    Ví dụ: `curl https://example.com`
11. **wget**: Tương tự như curl, wget cũng được sử dụng để tải xuống tài nguyên từ mạng.

    Ví dụ: `wget https://example.com/file.txt`
12. **ssh**: Dùng để thiết lập kết nối bảo mật với một máy chủ từ xa để thực hiện các thao tác từ xa.

    Ví dụ: `ssh username@remote_host`
13. **scp**: Dùng để sao chép tệp từ hoặc đến máy chủ từ xa thông qua SSH.

    Ví dụ: `scp file.txt username@remote_host:/path/to/destination`


# Process Monitoring

**Quản lý quá trình** là việc theo dõi và quản lý việc thực thi của các chương trình hoặc quá trình trên một hệ thống máy tính:

#### Công cụ Dòng Lệnh:

1. **`top`**: Cung cấp một cái nhìn thời gian thực về các quá trình hệ thống. Nó hiển thị sử dụng CPU, sử dụng bộ nhớ, các ID quá trình (PIDs) và nhiều hơn nữa. Nhấn `q` để thoát.
2. **`ps`**: Hiển thị thông tin về các quá trình đang chạy. Các tùy chọn thông dụng bao gồm:
   * `ps aux`: Liệt kê tất cả các quá trình.
   * `ps aux | grep tên_quá_trình`: Lọc các quá trình theo tên.
   * `ps -ef`: Một cách khác để liệt kê tất cả các quá trình.
   * `ps -eLf`: Hiển thị cả các luồng.
3. **`htop`**: Một công cụ xem quá trình tương tác tương tự như `top`, nhưng với các tính năng nâng cao hơn và tùy chọn tùy chỉnh tốt hơn.
4.  **`pgrep` và `pkill`**: Lệnh để tìm hoặc gửi tín hiệu cho các quá trình theo tên hoặc các thuộc tính khác.

    * `pgrep tên_quá_trình`: Tìm ID quá trình theo tên.
    * `pkill tên_quá_trình`: Chấm dứt quá trình theo tên.

    **`lsof`** là một công cụ mạnh mẽ để giám sát các tệp và thư mục được mở trên hệ thống, giúp bạn theo dõi và quản lý các quá trình một cách hiệu quả.

#### Tệp Nhật Ký:

1. **`/var/log/`**: Các nhật ký hệ thống cung cấp thông tin về các quá trình, lỗi và sự kiện hệ thống.&#x20;

#### Giám Sát Sử Dụng Tài Nguyên:

1. **Sử Dụng CPU**: Theo dõi sử dụng CPU để xác định các quá trình tiêu thụ tài nguyên CPU quá mức sử dụng công cụ như `top`, `htop`, hoặc các tiện ích giám sát hệ thống.
2. **Sử Dụng Bộ Nhớ**: Theo dõi sử dụng bộ nhớ để ngăn rò rỉ bộ nhớ và cạn kiệt tài nguyên sử dụng công cụ như `top`, `htop`, hoặc các tiện ích giám sát hệ thống.
3. **I/O đĩa**: Theo dõi I/O đĩa để xác định các quá trình gây ra hoạt động đĩa nặng và nhận diện các rào cản hiệu suất tiềm ẩn.

#### Automation and alerting - Tự Động Hóa và Cảnh Báo:

1. **Cron Jobs**: Lên lịch cho các tập lệnh để kiểm tra định kỳ trạng thái quá trình, sử dụng tài nguyên và sức khỏe hệ thống.
2. **Monitoring Systems**: Sử dụng các công cụ giám sát dành riêng như Nagios, Zabbix hoặc Prometheus để tự động hóa việc giám sát quá trình, thiết lập cảnh báo và theo dõi các chỉ số hệ thống trong thời gian thực.

#### Process Control - Kiểm Soát Quá Trình:

1. **Lệnh `kill`**: Chấm dứt một quá trình bằng cách gửi một tín hiệu.
   * `kill PID`: Chấm dứt một quá trình bằng PID của nó.
   * `kill -9 PID`: Chấm dứt một quá trình mạnh mẽ.
2. **Lệnh `killall`**: Chấm dứt các quá trình theo tên.
   * `killall tên_quá_trình`: Chấm dứt tất cả các quá trình có tên được chỉ định.

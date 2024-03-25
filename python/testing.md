---
description: >-
  Testing quan trọng vì nó giúp đảm bảo tính đúng đắn của mã nguồn và giảm thiểu
  lỗi trong quá trình phát triển và bảo trì ứng dụng.
---

# Testing

**Sử dụng framework testing nào để viết unit test?**

* Python cung cấp `unittest` là một framework testing cơ bản dựa trên xUnit, giúp viết và chạy các test case.
* `pytest` là một framework testing phổ biến và mạnh mẽ hơn, cung cấp nhiều tính năng tiện ích và linh hoạt hơn so với `unittest`.
* Trong `pytest`, có thể sử dụng fixtures để chuẩn bị dữ liệu hoặc trạng thái cần thiết cho các test case. Để tránh phụ thuộc vào dữ liệu
* Có thể tạo mocks data và stubs  bằng cách sử dụng các thư viện như `unittest.mock` hoặc `pytest-mock`

**Phân biệt giữa unit testing và integration testing:**

* **Unit testing:** Kiểm tra tính đúng đắn của từng phần riêng lẻ của mã nguồn.
* **Integration testing:** Kiểm tra sự tương tác và tính đúng đắn của các thành phần khi chúng làm việc cùng nhau.

**API endpoints trong ứng dụng Python:**

* Kiểm thử API endpoints trong ứng dụng Python bằng cách gửi các yêu cầu HTTP và kiểm tra phản hồi từ API.
* Để kiểm tra phản hồi của API endpoints, sử dụng các assertion để kiểm tra các thành phần như mã trạng thái (status code), dữ liệu trả về, headers, và các thông tin khác trong phản hồi từ API. Đảm bảo rằng các phản hồi phù hợp với kỳ vọng và đáp ứng các yêu cầu kiểm thử.

#### Selenium Testing:

* Selenium là một công cụ tự động hóa việc kiểm thử trang web, cho phép bạn kiểm tra  và đảm bảo chất lượng của ứng dụng web thông qua việc tự động hóa các hoạt động như nhập liệu, chạy các hành động trên giao diện người dùng, và kiểm tra các kết quả mong đợi.
* Viết các test case bằng cách sử dụng các API của Selenium WebDriver để mở trình duyệt, thực hiện các hành động trên giao diện người dùng, và kiểm tra kết quả mong đợi.
* Một số công cụ phổ biến cho tự động hóa testing là Jenkins, Travis CI, và GitLab CI/CD. Đây là các công cụ cho phép  quản lý, lập lịch, và chạy các test case tự động trong quy trình CI/CD.


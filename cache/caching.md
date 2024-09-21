---
description: >-
  Caching - cải thiện hiệu suất của ứng dụng (lưu trữ và tái sử dụng kết quả
  hoặc dữ liệu đã truy cập trước đó. iúp giảm thời gian phản hồi, tăng tốc độ
  truy xuất dữ liệu, và giảm tải cho nguồn dữ liệu.
---

# Caching Invalidation

Cache Invalidation là một phần quan trọng trong quản lý cache để đảm bảo tính nhất quán giữa cache và dữ liệu nguồn:

1. **Time-Based Expiration:**
   * **Mô Tả:** Đặt thời gian sống cho mỗi mục trong cache. Sau khi thời gian sống hết, mục đó sẽ được coi là hết hạn và tự động vô hiệu hóa.
   * **Ưu Điểm:** Đơn giản, dễ triển khai.
   * **Nhược Điểm:** Không linh hoạt khi dữ liệu nguồn thay đổi không theo chu kỳ thời gian cố định.
2. **Manual Invalidation:**
   * **Mô Tả:** Thực hiện vô hiệu hóa cache một cách thủ công khi dữ liệu nguồn thay đổi. Có thể được thực hiện thông qua API hoặc các phương thức quản trị.
   * **Ưu Điểm:** Linh hoạt, có thể được kích hoạt từ bất kỳ đâu.
   * **Nhược Điểm:** Dễ gây ra lỗi nếu quên vô hiệu hóa cache tại các điểm cần thiết.
3. **Event-Driven Invalidation:**
   * **Mô Tả:** Khi dữ liệu nguồn thay đổi, phát sinh một sự kiện và sử dụng sự kiện này để vô hiệu hóa cache tương ứng.
   * **Ưu Điểm:** Tự động và linh hoạt, cache chỉ được vô hiệu hóa khi cần thiết.
   * **Nhược Điểm:** Phức tạp hơn để triển khai, đặc biệt trong môi trường phân tán.
4. **Versioned Caching:**
   * **Mô Tả:** Mỗi mục trong cache được gắn với một phiên bản. Khi dữ liệu nguồn thay đổi, tăng giá trị phiên bản, làm vô hiệu hóa cache.
   * **Ưu Điểm:** Tính nhất quán cao và không cần phải xác định thời gian sống cứng nhắc.
   * **Nhược Điểm:** Cần phải quản lý và duy trì phiên bản.
5. **Lazy Loading:**
   * **Mô Tả:** Cache không được vô hiệu hóa ngay lập tức khi dữ liệu nguồn thay đổi, mà chỉ khi có yêu cầu truy xuất mới. Lúc này, cache sẽ được làm mới và cung cấp dữ liệu mới.
   * **Ưu Điểm:** Giảm thiểu tác động đến hiệu suất khi có thay đổi.
   * **Nhược Điểm:** Có thể dẫn đến việc truy xuất dữ liệu lỗi thời khi cache chưa được cập nhật.
6. **Global Reset:**
   * **Mô Tả:** Đặt một sự kiện hoặc thực hiện một hành động để làm mới toàn bộ cache khi có sự thay đổi.
   * **Ưu Điểm:** Đơn giản và hiệu quả trong một số trường hợp.
   * **Nhược Điểm:** Gây tác động lớn đến hiệu suất khi cần làm mới toàn bộ cache.

\

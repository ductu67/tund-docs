---
description: >-
  Memcache và Redis đều được sử dụng để lưu trữ dữ liệu tạm thời trong bộ nhớ
  (in-memory cache) để cải thiện hiệu suất của ứng dụng, đều hỗ trợ mô hình
  key-value để lưu trữ và truy xuất dữ liệu.
---

# Memcached vs Redis

**Khác Nhau khi Sử Dụng Memcache và Redis:**

1. **Loại Dữ Liệu Hỗ Trợ:**
   * **Memcache:** Chỉ hỗ trợ lưu trữ dữ liệu dưới dạng key-value, không hỗ trợ các loại dữ liệu phức tạp.
   * **Redis:** Hỗ trợ nhiều kiểu dữ liệu như strings, lists, sets, sorted sets, hashes, bitmaps, hyperloglogs, và đối tượng địa chỉ.
2. **Bảo Mật:**
   * **Memcache:** Không có tính năng bảo mật tích hợp. Cần phải thực hiện các biện pháp bảo mật từ phía ứng dụng.
   * **Redis:** Cung cấp cơ chế bảo mật tích hợp bao gồm mật khẩu (password), mã hóa dữ liệu, và xác thực.
3. **Lưu Trữ Dữ Liệu:**
   * **Memcache:** Dữ liệu được lưu trữ tạm thời và không được bảo vệ nếu có sự cố xãy ra. Không hỗ trợ lưu trữ dữ liệu trên đĩa.
   * **Redis:** Hỗ trợ lưu trữ dữ liệu trên đĩa (persistent storage), giúp đảm bảo tính an toàn và khả năng khôi phục dữ liệu sau khởi động lại.
4. **Chiến Lược Vô Hiệu Hóa Cache (Cache Invalidation):**
   * **Memcache:** Thường sử dụng thời gian sống (time-to-live) để vô hiệu hóa cache.
   * **Redis:** Cung cấp nhiều chiến lược vô hiệu hóa cache như time-based expiration, manual invalidation, event-driven invalidation, và versioned caching.
5. **Cộng Đồng và Hỗ Trợ:**
   * **Memcache:** Có cộng đồng lớn, nhưng ít tính năng hơn so với Redis.
   * **Redis:** Có cộng đồng mạnh mẽ và sự hỗ trợ đa dạng từ cộng đồng và doanh nghiệp.
6. **Tính Năng Khác:**
   * **Memcache:** Tập trung chủ yếu vào việc cache cơ bản và truy xuất nhanh chóng.
   * **Redis:** Cung cấp nhiều tính năng phức tạp như pub/sub, transaction, scripting, và mô hình dữ liệu đa dạng.

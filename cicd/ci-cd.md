---
description: >-
  CI/CD (Continuous Integration/Continuous Deployment) là một quy trình phát
  triển phần mềm tự động hóa, tập trung vào việc cung cấp sự liên tục và đồng
  nhất trong quá trình triển khai ứng dụng.
---

# Concept

1. **Continuous Integration (CI - Tích Hợp Liên Tục):**
   * **Mục Tiêu:** Đảm bảo rằng các phiên bản mới của mã nguồn được tích hợp và kiểm thử một cách tự động và thường xuyên.
   * **Quy Trình:**&#x20;
     * Tự động hóa quá trình tích hợp mã
     * Kiểm thử đơn vị và kiểm thự tự động
     * Báo cáo kết quả tích hợp
   * **Nhược điểm** khi triển khai CI bao gồm:
     * **Tính Phức Tạp:** phức tạp và đòi hỏi sự đầu tư lớn từ đội ngũ phát triển.
     * **Yêu Cầu Cơ Sở Hạ Tầng Mạnh Mẽ:** dự án cần có một cơ sở hạ tầng vững mạnh để đảm bảo tính ổn định và hiệu suất.
     * **Đào Tạo và Thay Đổi Văn Hóa:** Nhận thức và sự thay đổi văn hóa trong đội ngũ có thể làm chậm quá trình triển khai CI.
2. **Continuous Deployment (CD - Triển Khai Liên Tục):**
   * **Mục Tiêu:** Tự động hóa quá trình triển khai ứng dụng vào môi trường sản phẩm sau khi CI.
   * **Quy Trình:**&#x20;
     * Tự động hóa việc triển khai ứng dụng.
     * Kiểm thử tích hợp trước triển khai.
     * Triển khai tự động vào môi trường sản phẩm.
3. **Lợi Ích của CI/CD:**
   * **Giảm Lỗi và Rủi Ro:** Tích hợp và triển khai tự động giúp giảm số lượng lỗi và rủi ro trong mã nguồn.
   * **Tăng Tốc Phát Triển:** Quá trình CI/CD giúp tăng tốc quá trình phát triển và triển khai ứng dụng.
   * **Tính Nhất Quán:** Đảm bảo sự nhất quán giữa môi trường phát triển, thử nghiệm và sản phẩm.
   * **Tăng Hiệu Suất và Chất Lượng:** Việc tự động hóa giúp tăng hiệu suất, chất lượng mã và giảm thời gian giữa các phiên bản ứng dụng.
4. **Quy Trình Thực Hiện CI/CD:**
   * **Commit:** Làm thay đổi vào mã nguồn và commit vào hệ thống quản lý mã nguồn.
   * **Build:** CI server tự động kích hoạtBB build khi có commit mới. Tích hợp mã mới vào mã nguồn hiện tại và thực hiện kiểm thử đơn vị.
   * **Test:** Kiểm thử tự động để đảm bảo tính ổn định và chất lượng.
   * **Deploy:** Triển khai tự động phiên bản mới vào môi trường thử nghiệm và sau đó môi trường sản phẩm.
5. **Công Cụ Phổ Biến Trong CI/CD:**
   * **Jenkins, Travis CI, GitLab CI/CD, CircleCI:** Công cụ quản lý quy trình CI/CD.
   * **Docker, Kubernetes:** Công cụ hỗ trợ việc đóng gói ứng dụng và quản lý môi trường triển khai.

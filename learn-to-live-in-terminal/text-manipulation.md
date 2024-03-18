# Text Manipulation

**Text manipulation** là quá trình thao tác và biến đổi văn bản sử dụng các lệnh và công cụ có sẵn trong môi trường dòng lệnh. Các công cụ này cho phép bạn thực hiện các tác vụ như tìm kiếm, thay thế, cắt, ghép nối, sắp xếp và biến đổi dữ liệu văn bản một cách linh hoạt và hiệu quả.

1.  **grep**: Dùng để tìm kiếm các dòng văn bản chứa một mẫu cụ thể.

    Ví dụ: `grep "pattern" file.txt`
2.  **sed**: Dùng để thay đổi và xử lý văn bản dựa trên các quy tắc đã định sẵn.

    Ví dụ: `sed 's/old/new/' file.txt`
3.  **awk**: Dùng để xử lý và hiển thị dữ liệu văn bản theo cột và hàng.

    Ví dụ: `awk '{print $1, $2}' file.txt`
4.  **cut**: Dùng để cắt và trích xuất các phần của văn bản dựa trên các định dạng cụ thể.

    Ví dụ: `cut -d"," -f1 file.csv`
5.  **sort**: Dùng để sắp xếp các dòng văn bản theo thứ tự được chỉ định.

    Ví dụ: `sort file.txt`
6.  **tr**: Dùng để thay đổi hoặc xóa các ký tự trong văn bản.

    Ví dụ: `tr 'a-z' 'A-Z' < file.txt`
7.  **wc**: Dùng để đếm số dòng, từ và byte trong văn bản.

    Ví dụ: `wc -l file.txt`
8. **nl:** Dùng để đánh số dòng của tập tin.
9. **cat:** Tiện ích dòng lệnh để nối các tệp và in trên đầu ra tiêu chuẩn

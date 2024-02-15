# Immutable and mutable

**Python** cung cấp nhiều kiểu dữ liệu chuẩn, và chúng có thể được chia thành hai loại chính là kiểu dữ liệu có thể thay đổi được (mutable) và kiểu dữ liệu không thay đổi được (immutable). Dưới đây là một số kiểu dữ liệu quan trọng:

#### Kiểu dữ liệu không thay đổi được (immutable):

1. **int (integer):** Kiểu số nguyên, ví dụ: `x = 5`.
2. **float (floating-point):** Kiểu số thực, ví dụ: `y = 3.14`.
3. **str (string):** Kiểu chuỗi, ví dụ: `s = "Hello"`.
4. **tuple:** Kiểu dữ liệu giống list nhưng không thể thay đổi nội dung sau khi khởi tạo, ví dụ: `t = (1, 2, 3)`.

#### Kiểu dữ liệu có thể thay đổi được (mutable):

1. **list:** Danh sách, có thể thay đổi nội dung, ví dụ: `my_list = [1, 2, 3]`.
2. **dict (dictionary):** Từ điển, có thể thay đổi khóa và giá trị, ví dụ: `my_dict = {'key': 'value'}`.
3. **set:** Tập hợp, có thể thay đổi nội dung, ví dụ: `my_set = {1, 2, 3}`.
4. **bytearray:** Mảng byte có thể thay đổi nội dung, ví dụ: `b_array = bytearray([1, 2, 3])`.

**Kiểu dữ liệu không thay đổi được (imutable) bảo toàn giá trị ban đầu sau khi khởi tạo**, trong khi **kiểu dữ liệu có thể thay đổi (mutable) được cho phép thay đổi nội dung của chúng.** Sự khác biệt này quan trọng khi bạn làm việc với các thuật toán và cấu trúc dữ liệu, đặc biệt là trong bối cảnh xử lý dữ liệu lớn và hiệu suất của chương trình.

NOTE: List chậm hơn nhưng nó có thể được chỉnh sửa và tuple thì nhanh hơn, không thể thay đổi

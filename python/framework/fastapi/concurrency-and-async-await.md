# Concurrency and async / await

\
Concurrency và `async/await` là hai khái niệm quan trọng trong lập trình, đặc biệt là trong ngữ cảnh của lập trình bất đồng bộ trong Python.

1. **Concurrency (Song song):**
   * Là khả năng thực hiện nhiều tác vụ cùng một lúc.
   * Các tác vụ có thể chạy đồng thời (trong cùng một khoảng thời gian) hoặc có thể chuyển đổi giữa chúng để tận dụng thời gian CPU.
   * Concurrency có thể được thực hiện thông qua việc sử dụng nhiều luồng (threads) hoặc tiến trình (processes) trên hệ điều hành, hoặc thông qua cơ chế bất đồng bộ (async) trong lập trình Python.
2. **Async/Await (Bất đồng bộ):**
   * Là một mô hình lập trình cho phép thực hiện các tác vụ mà không làm chặn (block) luồng thực thi chính.
   * `async` và `await` là từ khoá trong Python để đánh dấu và chờ đợi các hàm hoặc coroutine (hàm bất đồng bộ).
   * Bất đồng bộ thường được sử dụng để xử lý các tác vụ I/O-bound (như đọc/ghi dữ liệu từ/đến cơ sở dữ liệu) mà không làm gián đoạn luồng chính, giúp tối ưu hóa hiệu suất khi có nhiều yêu cầu cần được xử lý đồng thời.
   * Có thể sử dụng `asyncio` trong Python để hỗ trợ lập trình bất đồng bộ.
